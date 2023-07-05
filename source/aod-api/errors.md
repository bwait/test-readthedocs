<h1 id="prodtitle" style="color: #33bbb9;">Audio On Demand (AOD) API <span class="General.API mc-variable"></span> 1.0</h1><hr width="100%" size="0" align="center" /><span class="MCBreadcrumbsPrefix">You are here: </span><span class="MCBreadcrumbs">Error Codes</span><p style="text-align: right;">
  <button onclick="clearBrowserCache()">Clear cache</button>
</p>

# Error Codes

The AOD API can experience situations where returning one or more error objects is the appropriate response.  This section describes the error object structure and the types of errors that can be encountered.

## Error Response Definition

A typical error is shown in the following example.

{
  "status": 400,
  "error": "invalid_query_parameter_value",
  "description": "Value for query parameter 'title' cannot be blank."
}

The table below describes the members of the object:

<table style="width: 100%;" class="TableStyle-Standard" cellspacing="0">
  <col style="width: 288px;" class="TableStyle-Standard-Column-Regular" />
  <col style="width: 69px;" class="TableStyle-Standard-Column-Regular" />
  <col class="TableStyle-Standard-Column-Regular" />
  <thead>
    <tr class="TableStyle-Standard-Head-Header1">
      <th class="TableStyle-Standard-HeadE-Regular-Header1">Field</th>
      <th class="TableStyle-Standard-HeadE-Regular-Header1">Data Type</th>
      <th class="TableStyle-Standard-HeadD-Regular-Header1">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr class="TableStyle-Standard-Body-Row1">
      <td class="TableStyle-Standard-BodyE-Regular-Row1">status</td>
      <td class="TableStyle-Standard-BodyE-Regular-Row1">integer</td>
      <td class="TableStyle-Standard-BodyD-Regular-Row1">Specifies an http status code for the error.</td>
    </tr>
    <tr class="TableStyle-Standard-Body-Row1">
      <td class="TableStyle-Standard-BodyE-Regular-Row1">error</td>
      <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
      <td class="TableStyle-Standard-BodyD-Regular-Row1">Code specifying error type. This field can be programmed for. Make sure your code handles any additional errors that may arise beyond those listed below.</td>
    </tr>
    <tr class="TableStyle-Standard-Body-Row1">
      <td class="TableStyle-Standard-BodyB-Regular-Row1">description</td>
      <td class="TableStyle-Standard-BodyB-Regular-Row1">string</td>
      <td class="TableStyle-Standard-BodyA-Regular-Row1">Human readable description of the error.</td>
    </tr>
  </tbody>
</table>
The following error fields are defined:

* "page_not_found"
* "resource_not_found"
* "invalid_query_parameter_key"
* "invalid_query_parameter_value"
* "invalid_request"
* "unauthorized_missing_api_key"
* "unauthorized_invalid_api_key"
* "unauthorized_invalid_entitlement_permissions"
* "plan_limit_exceeded"
* "rate_limit_exceeded"
* "quota_limit_exceeded"
* "request_too_large"
* "internal_server_error"
* "service_unavailable"
* "unexpected_eof_at_target"

If you are not able to resolve the errors noted, contact Gracenote customer support with the exact query and the errors in question.

<hr width="100%" size="0" align="center" />
