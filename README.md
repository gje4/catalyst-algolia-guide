## How to Integrate Algolia SearchBox into Catalyst


## **Introduction**
The introduction consists of 2-3 sentences to orient the reader. State the guide’s purpose.

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

1. Once you have catalyst running.  Grab the quick search files from here.
2. Add Algolia keys to .env.
`  ALGOLIA_APP_ID=
   ALGOLIA_APP_KEY=`
3. Import `npm i react-instantsearch` , `npm i -S algoliasearch`
4. Add the files algoliasearchbox.tsx and algoliasearchhits.tsx to QuickSearch componenet, https://github.com/gje4/catalyst-algolia/tree/main/components/quick-search
5. Update the code in index.tsx to use the code from here,
   https://github.com/gje4/catalyst-algolia/blob/main/components/quick-search/index.tsx.
6. Update the algoliaClient in index.tsx to use your correct indexName.  By default the Algolia BigCommerce app names the index BigCommerce.  You can then delete the _actions directory.
 <img width="446" alt="Screenshot 2024-02-21 at 3 00 12 PM" src="https://github.com/gje4/catalyst-algolia/assets/2981963/106cc009-67f3-40f6-a47f-bab68e491106">

 
7. Run the app pnpm run dev, and check the quick search box to see data returned from algolia.



## Resources
https://www.catalyst.dev/
https://www.algolia.com/doc/api-reference/widgets/instantsearch/js/

