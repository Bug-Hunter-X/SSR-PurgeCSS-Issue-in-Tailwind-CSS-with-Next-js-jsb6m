# Tailwind CSS PurgeCSS Issue with Server-Side Rendering (SSR)

This repository demonstrates a common bug encountered when using Tailwind CSS with frameworks like Next.js or Nuxt.js that employ server-side rendering (SSR).  The problem centers on Tailwind's PurgeCSS process failing to include CSS classes used within components rendered on the server.

## Bug Description

When PurgeCSS optimizes the CSS bundle, it mistakenly removes classes used by components that are rendered server-side.  Consequently, those components appear incorrectly styled on the client-side after the initial page load.  Missing styles, broken layouts, or unexpected visual discrepancies are the typical symptoms.

## Reproduction

The `bug.js` file contains a Next.js component example exhibiting this problem.  Run the Next.js development server, and observe the missing styles after the initial render.

## Solution

The `bugSolution.js` file provides a working solution. It addresses the core issue by making sure all the styles are properly included by PurgeCSS, even if they're only initially used in the server side render.