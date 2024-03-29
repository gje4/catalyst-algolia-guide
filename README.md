## How to Integrate Algolia SearchBox into Catalyst

## **Demo Site**
https://catalyst-algolia.vercel.app/


## **Introduction**

Developers can quickly integrate Algolia search into the BigCommerce frontend Catalyst to enable search across all products.
This guide walks through the basic integration and provides files that can be copy and pasted into Catalyst CORE app.


## **Prerequisites**
To complete the guide, you will need the following:
* A [Catalyst storefront set up](https://github.com/bigcommerce/catalyst)
* Experience using Next.js
* A BigCommerce Store with the [Algolia app](https://www.bigcommerce.com/apps/algolia-search-discovery/) installed
* An Algolia account


## Requirements
- Node.js 18+
- `npm` (or `pnpm`/`yarn`)

## **Steps**
1. Set up and have a Catalyst storefront running - [instructions available here](https://github.com/bigcommerce/catalyst)
2. Add the following Algolia keys, which you can find in your Algolia account, to the existing .env.local file in your Catalyst storefront repository. **_IF this is your first time using a new Algolia account, be sure to “regenerate” your Search Only API key before using it_**:
   * `NEXT_PUBLIC_ALGOLIA_APP_ID=`*YOUR_APP_ID*
   * `NEXT_PUBLIC_ALGOLIA_API_KEY=`*YOUR_SEARCH_ONLY_API_KEY*
4. Install the following dependencies in your repository:
   * `npm i react-instantsearch`
   * `npm i -S algoliasearch`
6. Add the files `algoliaSearchBox.tsx` and `algoliaSearchHits.tsx` to the [`quick-search`](https://github.com/gje4/catalyst-algolia/tree/main/components/quick-search) component folder
7. Update the code in `index.tsx` to use the code found [here](https://github.com/gje4/catalyst-algolia/blob/main/components/quick-search/index.tsx)
8. Update the `algoliaClient` in `index.tsx` to use your correct `indexName`.  By default, the Algolia <> BigCommerce app names the index `BigCommerce`
9. You can then delete the `_actions` directory so your file structure mirrors the screenshot below
<img width="468" alt="Screenshot 2024-02-26 at 3 37 57 PM" src="https://github.com/gje4/catalyst-algolia-guide/assets/2981963/c923dab5-5009-4983-91fa-1a3e76f294df">

 
10. Run the app by running `pnpm run dev`, and check the QuickSearch box to see the data returned from Algolia


## Resources
* https://www.catalyst.dev/
* https://www.algolia.com/doc/api-reference/widgets/instantsearch/js/

