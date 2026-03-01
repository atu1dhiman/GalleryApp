# GalleryApp

In this Gallery app, we are calling an API that returns around 5000 images, which need to be displayed in a gallery view with smooth loading and scrolling performance.

To handle this efficiently, we can approach it in two ways:

1. Lazy loading with in-memory caching (using NSCache) to load images on demand and avoid re-fetching or re-decoding during fast scrolling.
2. Pagination-based loading, where we limit the number of records appended to the data source based on scroll position, ensuring that even during aggressive fast scrolling, the UI remains smooth.

If the API does not support server-side pagination and returns the full dataset (non-paginated metadata), we can still implement client-side batching to progressively append items to the UI.

This approach should work effectively for a small-to-medium scale application, provided memory management, background decoding, and proper cell reuse strategies are implemented correctly.
