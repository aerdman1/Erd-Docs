---
title: Here Changelog Test
deprecated: false
hidden: false
icon: far fa-calendar-circle-exclamation
metadata:
  robots: index
---
<ChangelogMount
  maxItems={50}
  cacheMinutes={15}
  preconnectRss={true}
  fetchTimeoutMs={5000}
  hydrateFromPermalink={true}
  hydrateMax={20}
  hydrateConcurrency={4}
  minExcerptChars={120}
  excerptMaxChars={900}
  enableModal={true}
  modalContentSelector=".ChangelogPage_list-post"
  modalMaxWidth={980}
  showTypeFilter={true}
  showAuthorFilter={false}
  showSort={true}
  showSearch={true}
  showToc={false}
  showTitles={false}
  cardsPerRow={1}
  showPreview={true}
  previewMaxChars={280}
  showSeeMore={true}
  showProductFilter={true}
  showVersionFilter={true}
  showVersionOnCards={true}
  tocTitle="All changelogs"
  tocMaxHeightVh={72}
  initialRenderCount={5}
  autoLoadMore={false}
  renderBatchSize={10}
  renderIdleTimeoutMs={100}
  showDescriptions={false}
  rewriteVersionedChangelogLinks={true}
  stripQueryParamsForPostFetch={true}
  fallbackToIframeInModal={true}
  preferApiNextForModal={true}
  preferRenderedHtmlForModal={true}
  modalCacheMinutes={15}
  apiProjectSlug=""
  apiNextChangelogPath="/api-next/v2/changelogs/"
/>

<HTMLBlock>{`
<style>
section.content-toc.grid-25 { display: none; }

.rm-Guides .content-body{
  -ms-flex-negative: 1;
  flex-shrink: 1;
  max-width: 100%;
  padding-top: 30px;
  width: 100%;
}

.rmChangelogFeed__modalTitle {
  font-weight: 900;
  font-size: 16px;
  line-height: 1.2;
  max-width: 600px;
  margin: 0;
  display: block;
}
</style>
`}</HTMLBlock>
