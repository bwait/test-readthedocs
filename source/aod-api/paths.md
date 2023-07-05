<h1 id="prodtitle" style="color: #33bbb9;">Audio On Demand (AOD) API <span class="General.API mc-variable"></span> 1.0</h1><hr width="100%" size="0" align="center" /><span class="MCBreadcrumbsPrefix">You are here: </span><span class="MCBreadcrumbs">APIs</span><p style="text-align: right;">
  <button onclick="clearBrowserCache()">Clear cache</button>
</p>

# APIs

There are three requests to the AOD API. The links below require sign-in.

## GET /episodes

Use this URI to fetch podcast episodes. All published episodes until the current date and time are delivered in the output.
Results are limited to a maximum of 100 per page. For more information on usage and query parameters, including an interactive demonstration see:
[https://nlsn-gracenote-developer.apigee.io/docs/audio-on-demand/1/routes/episodes/get](https://nlsn-gracenote-developer.apigee.io/docs/audio-on-demand/1/routes/episodes/get)
## GET /series

Use this URI to fetch podcast series. Results are limited to a maximum of 100 per page. For more information on usage and query parameters, including an interactive demonstration, see:
[https://nlsn-gracenote-developer.apigee.io/docs/audio-on-demand/1/routes/series/get](https://nlsn-gracenote-developer.apigee.io/docs/audio-on-demand/1/routes/series/get)
## GET /categories

Use this URI to retrieve the hierarchical list of Gracenote category descriptor IDs and IDs that are used to annotate series and episode objects and their descriptive strings. All category descriptor objects are returned in a single response For more information on usage, see:
[https://nlsn-gracenote-developer.apigee.io/docs/audio-on-demand/1/routes/categories/get](https://nlsn-gracenote-developer.apigee.io/docs/audio-on-demand/1/routes/categories/get)
See the section [categories response](datadictionary.md#categories_response)  for details on the response.

<hr width="100%" size="0" align="center" />
