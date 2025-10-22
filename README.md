# SEC Common Stock Shares Outstanding Viewer

This application provides a dynamic view of a company's common stock shares outstanding data, fetched directly from the SEC EDGAR API. It highlights the maximum and minimum shares outstanding values reported after fiscal year 2020.

## Features

-   **Dynamic CIK Loading**: View data for different companies by specifying a CIK (Central Index Key) in the URL.
-   **Max/Min Value Highlighting**: Easily identify the highest and lowest reported shares outstanding.
-   **Responsive Design**: Built with Tailwind CSS for a modern, mobile-friendly interface.
-   **Real-time Updates**: Data is fetched and rendered without a full page reload when a CIK is specified via the URL.

## How to Use

1.  **Open `index.html`**: Simply open the `index.html` file in your web browser. By default, it will display data for **Biogen (CIK: 0000875045)**.

2.  **View Data for a Specific Company**: To view data for a different company, append a `CIK` query parameter to the URL.
    Example:
    `index.html?CIK=0001018724` (for Apple Inc.)

## Technical Details

The application uses JavaScript to:
-   Parse the CIK from the URL query string.
-   Fetch company concept data from the SEC EDGAR API (`https://data.sec.gov/api/xbrl/companyconcept/`). A CORS proxy (e.g., AllOrigins) is used to bypass potential cross-origin restrictions.
-   Filter the `EntityCommonStockSharesOutstanding` data for fiscal years (`fy`) greater than "2020".
-   Calculate and display the maximum and minimum shares outstanding values within the filtered dataset.
-   Update the page title and content dynamically.

## Development

This project uses Tailwind CSS for styling, included via a CDN for simplicity. No build step is required for the CSS.