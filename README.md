# React Router Dom Catch-all Route Issue

This repository demonstrates an unexpected behavior in React Router Dom v6 related to catch-all routes (`/*`).  The issue arises when a catch-all route is placed after more specific routes.  Even if a request matches one of the specific paths, the catch-all route will still be triggered resulting in unwanted 404 pages.

## Problem

The provided `App.js` file contains a simple React Router setup with three routes:
- `/`: Home page
- `/about`: About page
- `/*`: Catch-all (Not Found) page

The expectation is that requests to `/` or `/about` should render the corresponding components.  However, due to the bug, requests to `/` or `/about` will be handled by the catch-all route leading to a `NotFound` component being rendered.

## Solution

The solution is to rearrange the routes to place the catch-all route as the last route defined. This ensures that only routes which don't match other, more specific routes will fall into the catch-all.