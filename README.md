**Guide**
# Integrating Algolia SearchBox into Catalyst

You can integrate Algolia search into Catalyst storefronts to help shoppers search all products, categories, and more.

This guide demonstrates a basic integration and provides example code for global product search that you can add to the core code of your Catalyst storefront, or to `apps/core` in the Catalyst [monorepo](/docs/monorepo).

## Demo site

For a working demo of an Algolia integration with Catalyst, see the following example:

```shell copy
https://catalyst-algolia.vercel.app/
```

## Prerequisites

To follow this guide, you need the following:

* Node.js 18+
* A Node.js package manager, such as `npm`, `pnpm`, or `yarn`
* Working knowledge of [Next.js](https://nextjs.org)
* An [Algolia account](https://dashboard.algolia.com/users/sign_up)
* A [BigCommerce store](https://www.bigcommerce.com/start-your-trial/) or [sandbox store](https://start.bigcommerce.com/developer-sandbox/)

## Steps

1. Configure the core codebase for the Catalyst storefront and get it running in dev mode. See [CLI setup](/docs/cli) for quickstart instructions. If you configure Catalyst using the [Monorepo](/docs/monorepo), make sure the storefront is [associated with a BigCommerce store channel](https://developer.bigcommerce.com/docs/storefront/headless/channels).

2. At the top of your [Algolia dashboard](https://dashboard.algolia.com), create an Algolia app that you intend to associate exclusively with your Catalyst storefront channel.

3. Install the [BigCommerce Algolia app](https://www.bigcommerce.com/apps/algolia-search-discovery/) and associate it with your Catalyst channel. Add the following Algolia-specific environment variables to the existing `.env.local` file in your Catalyst storefront. For more about other Catalyst environment variables, see [Environment variables](/docs/environment-variables).

| Environment variable | Value |
|:---------------------|:------|
| `NEXT_PUBLIC_ALGOLIA_APP_ID` | Your Algolia app ID |
| `NEXT_PUBLIC_ALGOLIA_API_KEY` | Your Algolia Search Only API key. You can find this value in the **API keys > All API keys** section of your [Algolia account dashboard](https://dashboard.algolia.com/account/api-keys/restricted). If this is your first time using the new Algolia app, visit the **Search > Index** section of the Algolia dashboard and click the **Refresh index** button to generate your search index. |

4. Install the following dependencies in your Catalyst storefront:

```shell copy
  npm i react-instantsearch
  npm i -S algoliasearch
```

5. Clone the [Algolia example repo](https://github.com/gje4/catalyst-algolia) in a directory parallel to your Catalyst storefront. Copy the `quick-search` directory into your Catalyst `components` directory.

```shell copy
git clone https://github.com/gje4/catalyst-algolia
cd catalyst-algolia
cp components/quick-search ../my-catalyst-storefront/components/quick-search
cd ../my-catalyst-storefront/components/quick-search
```

Your storefront's file tree will mirror the following screenshot.

[!A file tree with a components/quick-seach directory that contains the same files as the Algolia example repo](https://storage.googleapis.com/bigcommerce-production-dev-center/images/catalyst/algolia/algolia-integration-file-tree.png)

6. In `components/quick-search/index.tsx`, update the value of `algoliaClient` to use your correct `indexName`. By default, the BigCommerce Algolia app names the search index `BigCommerce`.

7.  Start your Catalyst storefront app in dev mode. Check the QuickSearch box to see the data supplied by the Algolia app index.

```shell copy
pnpm run dev
```

## Resources

* [Catalyst core docs](https://www.catalyst.dev/docs)
* [Algolia search widget docs](https://www.algolia.com/doc/api-reference/widgets/instantsearch/js/)
