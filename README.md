## How to Integrate Algolia SearchBox into Catalyst

## **Demo Site**
https://catalyst-algolia.vercel.app/


## **Introduction**

Developers can quickly integrate Algolia search into the BigCommerce frontend Catalyst to enable search across all products.
This guide walks through the basic integration and provides files that can be copy and pasted into Catalyst CORE app.


## **Prerequisites**
To complete the guide, you will need the following:
A BigCommerce Store with the algolia app installed, https://www.bigcommerce.com/apps/algolia-search-discovery/
An Algolia account

Catalyst setup, https://github.com/bigcommerce/catalyst

Experience using Next.js


## Requirements

- Node.js 18+
- `npm` (or `pnpm`/`yarn`)

## **Steps**

1. Setup and have catalyst running, https://github.com/bigcommerce/catalyst.
2. Add Algolia keys to .env.
`  ALGOLIA_APP_ID=
   ALGOLIA_APP_KEY=`
3. Import `npm i react-instantsearch` , `npm i -S algoliasearch`
4. Add the files algoliasearchbox.tsx and algoliasearchhits.tsx to QuickSearch componenet, https://github.com/gje4/catalyst-algolia/tree/main/components/quick-search
5. Update the code in index.tsx to use the code from here,
   https://github.com/gje4/catalyst-algolia/blob/main/components/quick-search/index.tsx.
6. Update the algoliaClient in index.tsx to use your correct indexName.  By default the Algolia BigCommerce app names the index BigCommerce.  You can then delete the _actions directory.
<img width="468" alt="Screenshot 2024-02-26 at 3 37 57 PM" src="https://github.com/gje4/catalyst-algolia-guide/assets/2981963/c923dab5-5009-4983-91fa-1a3e76f294df">

 
7. Run the app pnpm run dev, and check the quick search box to see data returned from algolia.



## Resources
https://www.catalyst.dev/
https://www.algolia.com/doc/api-reference/widgets/instantsearch/js/

