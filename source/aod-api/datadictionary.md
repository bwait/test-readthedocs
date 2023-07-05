<h1 id="prodtitle" style="color: #33bbb9;">Audio On Demand (AOD) API <span class="General.API mc-variable"></span> 1.0</h1><hr width="100%" size="0" align="center" /><span class="MCBreadcrumbsPrefix">You are here: </span><span class="MCBreadcrumbs">Data Dictionary</span><p style="text-align: right;">
  <button onclick="clearBrowserCache()">Clear cache</button>
</p>

# Data Dictionary

This section provides examples of data found in the responses. In addition to the below responses, errors can also be returned.  See the [Audio On Demand (AOD) API  1.0](errors.md#top) section for more information.

## audioEnclosure

### Example

"audioEnclosure": {
  "audioUrl": "https://dts.podtrac.com/redirect.mp3/rss.art19.com/episodes/09cab66f-80e7-285436f40422.mp3",
  "mimeType": "audio/mpeg",
  "sizeBytes": 5931676
},

<p>
  <p>
    <h3>Member Definition</h3>
    <table style="width: 100%;" class="TableStyle-Standard" cellspacing="0">
      <col style="width: 288px;" class="TableStyle-Standard-Column-Regular" />
      <col class="TableStyle-Standard-Column-Regular" />
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
          <td class="TableStyle-Standard-BodyE-Regular-Row1">audioEnclosure</td>
          <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
          <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing data.</td>
        </tr>
        <tr class="TableStyle-Standard-Body-Row1">
          <td class="TableStyle-Standard-BodyE-Regular-Row1">audioUrl</td>
          <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
          <td class="TableStyle-Standard-BodyD-Regular-Row1">The URL of the audio file.</td>
        </tr>
        <tr class="TableStyle-Standard-Body-Row1">
          <td class="TableStyle-Standard-BodyE-Regular-Row1">mimeType</td>
          <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
          <td class="TableStyle-Standard-BodyD-Regular-Row1">The mime type of the URL.</td>
        </tr>
        <tr class="TableStyle-Standard-Body-Row1">
          <td class="TableStyle-Standard-BodyB-Regular-Row1">sizeBytes</td>
          <td class="TableStyle-Standard-BodyB-Regular-Row1">integer</td>
          <td class="TableStyle-Standard-BodyA-Regular-Row1">Size of the data the URL points to in bytes.</td>
        </tr>
      </tbody>
    </table>
    <h2>
      <a name="available"></a>availabilities</h2>
    <p>
      <h3>Example</h3>
      <p>
        <pre class="prettyprint">
"availabilities": [
  {
    "license": "Open",
    "name": "All" 
  }<br />]<br /></pre>
      </p>
      <h3>Member Definition</h3>
      <table style="width: 100%;" class="TableStyle-Standard" cellspacing="0">
        <col style="width: 288px;" class="TableStyle-Standard-Column-Regular" />
        <col class="TableStyle-Standard-Column-Regular" />
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
            <td class="TableStyle-Standard-BodyE-Regular-Row1">availabilities</td>
            <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
            <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing data.</td>
          </tr>
          <tr class="TableStyle-Standard-Body-Row1">
            <td class="TableStyle-Standard-BodyE-Regular-Row1">license</td>
            <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
            <td class="TableStyle-Standard-BodyD-Regular-Row1">License type. This can be either "Open" or "Licensed". If this value is blank or null, that also indicates an open license. If the podcast is an exclusive it is licensed with the host details within name.</td>
          </tr>
          <tr class="TableStyle-Standard-Body-Row1">
            <td class="TableStyle-Standard-BodyB-Regular-Row1">name</td>
            <td class="TableStyle-Standard-BodyB-Regular-Row1">string</td>
            <td class="TableStyle-Standard-BodyA-Regular-Row1">Indicates the host name who owns the licenses to the podcast. Open podcasts (non-exclusives) are indicated by "All".</td>
          </tr>
        </tbody>
      </table>
    </p>
    <h2>
      <a name="categori"></a>categories </h2>
    <p>Categories describes the "categories" object returned within the data of a get /series or get /episodes request.</p>
    <h3>Categories in Episodes</h3>
    <ul>
      <li>
        <span class="MCTextPopup">
          <a class="MCTextPopupSpot_0">Enriched<img style="border: none;margin-left: 5px;" src="../SkinSupport/ExpandingClosed.gif" onload="if ( typeof( FMCPreloadImage ) == 'function' ) { FMCPreloadImage( '../SkinSupport/ExpandingOpen.gif' ); }" alt="Closed" class="MCExpandingIcon" /></a>
          <span class="MCTextPopupBody_0">Indicates data that has been added to an episode's information by a Gracenote editor.</span>
        </span> episodes with status <b>Enhanced</b> have editorially assigned categories for episodes.</li>
      <li>Episodes with status <b>Original</b>.- Publishers do not categorize episodes. Therefore episodes that have not been editorially enhanced do not have categories assigned.</li>
    </ul>
    <h3>Categories in Series</h3>
    <ul>
      <li>Enriched series with status - Enhanced have at least one to a maximum of three L1 categories assigned to the series and most relevant L2 and L3 granular categories assigned. There is no weighting to the first, second, or third category assigned as all assigned categories are equally relevant for the series. For example, a podcast series may be categorized as a Comedy &amp;gt;&amp;gt; Comedy interview and also Sports &amp;gt;&amp;gt; Football as it is a comedy interview discussing football in a comic way.</li>
      <li>For series that are not enhanced - podcast publisher defined categories for the series are mapped to the Gracenote category taxonomy to provide common category IDs across the entire dataset.</li>
    </ul>
    <p>
      <h3>Example</h3>
      <p>
        <pre class="prettyprint">	
"categories": [
  [
    {
      "level": 1,
      "descriptorID": "90270",
      "display": "Lifestyle"
    },
    {
      "level": 2,
      "descriptorID": "90368",
      "display": "Nerd Culture"
    }
  ],<br />  [
    {
      "level": 1,<br />      "descriptorID": "90270",
      "display": "Lifestyle"
    },
    {
      "level": 2,
      "descriptorID": "90388",
      "display": "Games"
    },
    {
      "level": 3,
      "descriptorID": "90708",
      "display": "RPG"    
    }
  ],
  [
    {
      "level": 1,
      "descriptorID": "90277",
      "display": "Storytelling"
    },<br />    {	<br />      "level": 2,
      "descriptorID": "90482",
      "display": "Fantasy"<br />    }
  ]
],						</pre>
      </p>
    </p>
    <h3>Member Definition</h3>
    <table style="width: 100%;" class="TableStyle-Standard" cellspacing="0">
      <col style="width: 288px;" class="TableStyle-Standard-Column-Regular" />
      <col class="TableStyle-Standard-Column-Regular" />
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
          <td class="TableStyle-Standard-BodyE-Regular-Row1">categories</td>
          <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
          <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing category and level descriptors.</td>
        </tr>
        <tr class="TableStyle-Standard-Body-Row1">
          <td class="TableStyle-Standard-BodyE-Regular-Row1">descriptorID</td>
          <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
          <td class="TableStyle-Standard-BodyD-Regular-Row1">The ID number of the descriptor. Descriptor IDs can be listed with the get /categories request.</td>
        </tr>
        <tr class="TableStyle-Standard-Body-Row1">
          <td class="TableStyle-Standard-BodyE-Regular-Row1">display</td>
          <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
          <td class="TableStyle-Standard-BodyD-Regular-Row1">Display text for the associated descriptor.</td>
        </tr>
        <tr class="TableStyle-Standard-Body-Row1">
          <td class="TableStyle-Standard-BodyB-Regular-Row1">level</td>
          <td class="TableStyle-Standard-BodyB-Regular-Row1">object</td>
          <td class="TableStyle-Standard-BodyA-Regular-Row1">The level number of the category. Levels go from 1 to 3.</td>
        </tr>
      </tbody>
    </table>
    <h2>
      <a name="categories_response"></a>categories response</h2>
    <p>Categories response describes the data that is returned by the get /categories request.</p>
    <p>This response is a hierarchical list of Gracenote category descriptor taxonomy with IDs that are used to annotate series and episode objects and their descriptive strings.</p>
    <p>
      <h3>Example<br /></h3>
      <p> Note that there can be multiple children per level, each containing their own descriptorIDs.</p>
      <p>
        <pre class="prettyprint">
{
  "meta": {
    "total": 1,
    "count": 1,
    "offset": 0
  },						
  "data": [
    {
      "language": "en",
      "list": "AUDIO-ON-DEMAND",
      "revision": "1",
      "children": [
        {
          "descriptorID": "90264",
          "display": "Business",
          "level": 1,
          "children": [
            {
              "descriptorID": "90295",
              "display": "Successful People",
              "level": 2,
              "children": [
                {
                  "descriptorID": "90564",
                  "display": "Women In Business",
                  "level": 3,
                  "children": [
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  }
}
</pre>
      </p>
      <h3>Member Definition</h3>
      <table style="width: 100%;" class="TableStyle-Standard" cellspacing="0">
        <col style="width: 288px;" class="TableStyle-Standard-Column-Regular" />
        <col class="TableStyle-Standard-Column-Regular" />
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
            <td class="TableStyle-Standard-BodyE-Regular-Row1">children</td>
            <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
            <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing field level information, from the three associated levels.</td>
          </tr>
          <tr class="TableStyle-Standard-Body-Row1">
            <td class="TableStyle-Standard-BodyE-Regular-Row1">data</td>
            <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
            <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing categories data.</td>
          </tr>
          <tr class="TableStyle-Standard-Body-Row1">
            <td class="TableStyle-Standard-BodyE-Regular-Row1">descriptorID</td>
            <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
            <td class="TableStyle-Standard-BodyD-Regular-Row1">Level descriptor ID number.</td>
          </tr>
          <tr class="TableStyle-Standard-Body-Row1">
            <td class="TableStyle-Standard-BodyE-Regular-Row1">display</td>
            <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
            <td class="TableStyle-Standard-BodyD-Regular-Row1">Display text for the associated code.</td>
          </tr>
          <tr class="TableStyle-Standard-Body-Row1">
            <td class="TableStyle-Standard-BodyE-Regular-Row1">language</td>
            <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
            <td class="TableStyle-Standard-BodyD-Regular-Row1">Language for the results.</td>
          </tr>
          <tr class="TableStyle-Standard-Body-Row1">
            <td class="TableStyle-Standard-BodyE-Regular-Row1">level</td>
            <td class="TableStyle-Standard-BodyE-Regular-Row1">integer</td>
            <td class="TableStyle-Standard-BodyD-Regular-Row1">The level of this category ID, from one to three.</td>
          </tr>
          <tr class="TableStyle-Standard-Body-Row1">
            <td class="TableStyle-Standard-BodyE-Regular-Row1">list</td>
            <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
            <td class="TableStyle-Standard-BodyD-Regular-Row1">Name of the data list.</td>
          </tr>
          <tr class="TableStyle-Standard-Body-Row1">
            <td class="TableStyle-Standard-BodyE-Regular-Row1">meta</td>
            <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
            <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing paging information. See <a href="#response" class="MCXref_0">responseMeta</a> for more information.</td>
          </tr>
          <tr class="TableStyle-Standard-Body-Row1">
            <td class="TableStyle-Standard-BodyB-Regular-Row1">revision</td>
            <td class="TableStyle-Standard-BodyB-Regular-Row1">string</td>
            <td class="TableStyle-Standard-BodyA-Regular-Row1">Revision number of this list.</td>
          </tr>
        </tbody>
      </table>
      <p> </p>
    </p>
  </p>
  <h2>
    <a name="credits"></a>credits</h2>
</p>

<p>
  <p>
    <h3>Example</h3>
    <pre class="prettyprint">"credits": [<br />  {<br />    "name": "Anders Kelto",<br />    "personID": "1314514",<br />    "role": {<br />        "display": "Host"
    },
  }<br />]<br /></pre>
  </p>
  <p>
    <h3>Member Definition</h3>
    <table style="width: 100%;" class="TableStyle-Standard" cellspacing="0">
      <col style="width: 288px;" class="TableStyle-Standard-Column-Regular" />
      <col class="TableStyle-Standard-Column-Regular" />
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
          <td class="TableStyle-Standard-BodyE-Regular-Row1">credits</td>
          <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
          <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing data.</td>
        </tr>
        <tr class="TableStyle-Standard-Body-Row1">
          <td class="TableStyle-Standard-BodyE-Regular-Row1">display</td>
          <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
          <td class="TableStyle-Standard-BodyD-Regular-Row1">The name of the role. The following values are available:<ul><li>Host</li><li>Co-host</li><li>Guest</li><li>Reporter</li><li>Speaker</li><li>Voice Performer</li><li>Musical Performer / Mix DJ</li><li>Participant</li><li>Sourced Audio</li><li>Subject</li></ul></td>
        </tr>
        <tr class="TableStyle-Standard-Body-Row1">
          <td class="TableStyle-Standard-BodyE-Regular-Row1">name</td>
          <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
          <td class="TableStyle-Standard-BodyD-Regular-Row1">The name of the person occupying this role.</td>
        </tr>
        <tr class="TableStyle-Standard-Body-Row1">
          <td class="TableStyle-Standard-BodyE-Regular-Row1">personID</td>
          <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
          <td class="TableStyle-Standard-BodyD-Regular-Row1">The Gracenote identifying string for this person. This is the same person ID as in the Gracenote Celebrity and Enhanced Celebrity products and can be looked up in the Celebrity products for images and bios.</td>
        </tr>
        <tr class="TableStyle-Standard-Body-Row1">
          <td class="TableStyle-Standard-BodyB-Regular-Row1">role</td>
          <td class="TableStyle-Standard-BodyB-Regular-Row1">object</td>
          <td class="TableStyle-Standard-BodyA-Regular-Row1">The associated  role.</td>
        </tr>
      </tbody>
    </table>
    <p>
      <p>
        <h2>episode</h2>
        <p>
          <h3>Example</h3>
          <p>
            <pre class="prettyprint">
{
  "audioEnclosure": {
    "audioUrl": "https://dts.podtrac.com/redirect.mp3/rss.art19.com/episodes/09cab66f-80e7-285436f40422.mp3",
    "mimeType": "audio/mpeg",
    "sizeBytes": 5931676
  },
  "categories": [
    [
      {
        "descriptorID": "90276",
        "display": "Sports",
        "level": 1
      },
      {<br />        "descriptorID": "90454",
        "display": "Sports News",
        "level": 2
      }
    ],
    [
      {
        "descriptorID": "90276",
        "display": "Sports",
        "level": 1
      },
      {
        "descriptorID": "90455",
        "display": "Sports Talk",
        "level": 2
      }
    ]
  ],
  "credits": [
    {
      "name": "Anders Kelto",
      "personID": "1314514",
      "role": {
        "display": "Host"
      }
    },
    {
      "name": "Kavitha A. Davidson",
      "personID": "1314515",
      "role": {
        "display": "Host"
      }
    }<br />  ],
  "description": "wondery.fm/TheLead The Lead is a daily sports podcast from Wondery and The Athletic. Every weekday morning, The Lead brings you sports stories of the day from The Athletic’s team of local and national sports reporters. Stories like “Where did the 49ers new star running back, Raheem Mostert, come from?” or “What can Zion Williamson do for the Pelicans?”",
  "durationSeconds": 370,<br />  "editorialStatus": "enhanced",<br />  "episodeID": "GA0000P00101Pth",
  "episodeNumber": null,
  "availabilities": [
    {
      "license": "Open",
      "name": "All"
    }
  ],<br />  "language": "en",<br />  "lastUpdateDateTime": "2020-08-24T02:56:12Z",<br />  "objectType": "episode",
  "publishDateTime": "2020-01-29T08:00:00Z",
  "sourceFeed": {
    "description": "&amp;lt;p&amp;gt;wondery.fm/TheLead&amp;lt;/p&amp;gt;&amp;lt;p&amp;gt;The Lead is a daily sports podcast from Wondery and The Athletic. Every weekday morning, The Lead brings you sports stories of the day from The Athletic’s team of local and national sports reporters. Stories like “Where did the 49ers new star running back, Raheem Mostert, come from?” or “What can Zion Williams do for the Pelicans?”&amp;lt;/p&amp;gt;",
    "episodeType": "trailer",
    "explicitLanguage": false,
    "imageUrl": "https://content.production.cdn.art19.com/images/3e/fe/50/12/c10/ffe43.jpeg",
    "websiteUrl": null
  },
  "seasonNumber": null,
  "seriesID": "GA0000N0000030W",
  "subtitle": null,
  "summary": "wondery.fm/TheLead\n\nThe Lead is a daily sports podcast from Wondery and The Athletic. Every weekday morning, The Lead brings you sports stories of the day from The Athletic’s team of local and national sports reporters. Stories like “Where did the 49ers new star running back, Raheem Mostert, come from?” or “What can Zion Williams do for the Pelicans?”",
  "title": "Introducing The Lead: A Daily Sports Podcast"
},</pre> </p>
          <h3>Member Definition</h3>
          <table style="width: 100%;" class="TableStyle-Standard" cellspacing="0">
            <col style="width: 288px;" class="TableStyle-Standard-Column-Regular" />
            <col class="TableStyle-Standard-Column-Regular" />
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
                <td class="TableStyle-Standard-BodyE-Regular-Row1">audioEnclosure</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">See the <a href="#audioEnc" class="MCXref_0">audioEnclosure</a> description above. </td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">availabilities</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">The license type for this episode.  See the section on <a href="#available" class="MCXref_0">availabilities</a> for details.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">categories</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing level information for the episode. This object contains level one through three descriptor levels. See the section on <a href="#categori" class="MCXref_0">categories </a> for details.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">credits</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">object. </td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">
                  <span class="MCTextPopup">
                    <a class="MCTextPopupSpot_0">Credit<img style="border: none;margin-left: 5px;" src="../SkinSupport/ExpandingClosed.gif" onload="if ( typeof( FMCPreloadImage ) == 'function' ) { FMCPreloadImage( '../SkinSupport/ExpandingOpen.gif' ); }" alt="Closed" class="MCExpandingIcon" /></a>
                    <span class="MCTextPopupBody_0">An annotation of a job with an associated name.</span>
                  </span> objects for individuals present on the series. See the section on <a href="#credits" class="MCXref_0">credits</a> for details.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">description</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">Description of the episode.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">durationSeconds</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">integer</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">Duration of the episode in seconds.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">editorialStatus</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">enum</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">
                  <span class="MCTextPopup">
                    <a class="MCTextPopupSpot_0">Status<img style="border: none;margin-left: 5px;" src="../SkinSupport/ExpandingClosed.gif" onload="if ( typeof( FMCPreloadImage ) == 'function' ) { FMCPreloadImage( '../SkinSupport/ExpandingOpen.gif' ); }" alt="Closed" class="MCExpandingIcon" /></a>
                    <span class="MCTextPopupBody_0">Indicates enhanced when Gracenote adds editorial metadata.</span>
                  </span> of the episode: "enhanced" to indicate a podcast with verified Gracenote-enhanced data and "original" to indicate a non verified podcast.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">episodeID</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">The <span class="MCTextPopup"><a class="MCTextPopupSpot_0">Gracenote ID<img style="border: none;margin-left: 5px;" src="../SkinSupport/ExpandingClosed.gif" onload="if ( typeof( FMCPreloadImage ) == 'function' ) { FMCPreloadImage( '../SkinSupport/ExpandingOpen.gif' ); }" alt="Closed" class="MCExpandingIcon" /></a><span class="MCTextPopupBody_0">A unique alphanumeric code that identifies a specific person, place, or thing stored within the Gracenote database.</span></span> code for this episode.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">episodeNumber</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">integer</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">The numeric episode number. Can have a null value.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">language</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">Two-letter code for language of the podcast in ISO-639-1 standard.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">lastUpdateDateTime</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">Last update time stamp for the episode in ISO 8601 format.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">objectType</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">Field indicating if this is a series or episode.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">sourceFeed</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">Information about the episode that is available within the RSS feed as provided by the content creator. See the section on <a href="#sourceFeed" class="MCXref_0">sourceFeed</a>  for more details.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">seasonNumber</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">
                  <span class="MCTextPopup">
                    <a class="MCTextPopupSpot_0">Season<img style="border: none;margin-left: 5px;" src="../SkinSupport/ExpandingClosed.gif" onload="if ( typeof( FMCPreloadImage ) == 'function' ) { FMCPreloadImage( '../SkinSupport/ExpandingOpen.gif' ); }" alt="Closed" class="MCExpandingIcon" /></a>
                    <span class="MCTextPopupBody_0">A set of episodes for a series that was created during a specified time period.</span>
                  </span> number of series that this episode occurred in. </td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">seriesID</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">Gracenote code for the series this episode belongs to.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">subtitle</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">A subtitle for the episode, if it exists.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyE-Regular-Row1">summary</td>
                <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                <td class="TableStyle-Standard-BodyD-Regular-Row1">A summary of the episode, when available.</td>
              </tr>
              <tr class="TableStyle-Standard-Body-Row1">
                <td class="TableStyle-Standard-BodyB-Regular-Row1">title</td>
                <td class="TableStyle-Standard-BodyB-Regular-Row1">string</td>
                <td class="TableStyle-Standard-BodyA-Regular-Row1">
                  <span class="MCTextPopup">
                    <a class="MCTextPopupSpot_0">Title<img style="border: none;margin-left: 5px;" src="../SkinSupport/ExpandingClosed.gif" onload="if ( typeof( FMCPreloadImage ) == 'function' ) { FMCPreloadImage( '../SkinSupport/ExpandingOpen.gif' ); }" alt="Closed" class="MCExpandingIcon" /></a>
                    <span class="MCTextPopupBody_0">The name of the podcast episode.</span>
                  </span> of the episode.</td>
              </tr>
            </tbody>
          </table>
        </p>
      </p>
      <p>
        <h2>
          <a name="response"></a>responseMeta</h2>
      </p>
      <p>This field displays current positioning in the list of responses.</p>
      <p>
        <h3>Example</h3>
        <p>
          <pre class="prettyprint">
"meta": {
  "total": 8,
  "count": 8,
  "offset": 0
},</pre>
        </p>
        <h3>Member Definition</h3>
        <table style="width: 100%;" class="TableStyle-Standard" cellspacing="0">
          <col style="width: 288px;" class="TableStyle-Standard-Column-Regular" />
          <col class="TableStyle-Standard-Column-Regular" />
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
              <td class="TableStyle-Standard-BodyE-Regular-Row1">count</td>
              <td class="TableStyle-Standard-BodyE-Regular-Row1">integer</td>
              <td class="TableStyle-Standard-BodyD-Regular-Row1">Count of responses so far.</td>
            </tr>
            <tr class="TableStyle-Standard-Body-Row1">
              <td class="TableStyle-Standard-BodyE-Regular-Row1">meta</td>
              <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
              <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing data.</td>
            </tr>
            <tr class="TableStyle-Standard-Body-Row1">
              <td class="TableStyle-Standard-BodyE-Regular-Row1">offset</td>
              <td class="TableStyle-Standard-BodyE-Regular-Row1">integer</td>
              <td class="TableStyle-Standard-BodyD-Regular-Row1">Offset into the list of responses.</td>
            </tr>
            <tr class="TableStyle-Standard-Body-Row1">
              <td class="TableStyle-Standard-BodyB-Regular-Row1">total</td>
              <td class="TableStyle-Standard-BodyB-Regular-Row1">integer</td>
              <td class="TableStyle-Standard-BodyA-Regular-Row1">Total number of responses.</td>
            </tr>
          </tbody>
        </table>
        <p>
          <h2>
            <a name="sourceFeed"></a>sourceFeed</h2>
          <p>
            <h3>Example for Series</h3>
            <p>
              <pre class="prettyprint">
"sourceFeed": {
  "author": "Mission To Zyxx",
  "categories": [
    "Comedy",<br />    "Arts"
  ],
  "contentType": "Episodic",
  "copyright": "2017-2019 Zyxx Quadrant LLC",
  "description": "An improvised science fiction sitcom following a team of ambassadors as they attempt to establish diplomatic relations with planets in the remote and chaotic Zyxx Quadrant… better known as the \"ass end of space.\"",
  "explicitLanguage": true,
  "feedUrl": "https://feeds.simplecast.com/ZL7iUDiH",<br />  "generator": "https://simplecast.com",
  "imageUrl": "https://cdn.simplecast.com/images/fcda2e3f66e8/3000x3000/mrt.jpg?&amp;amp;Paid=rss_feed",<br />  "keywords:[<br />    "surgery",<br />    "pain",<br />    "doctor",<br />    "medicine"<br />  ]    <br />  "owner": "Mission To Zyxx",
  "websiteUrl": "https://missiontozyxx.space/"
}</pre> </p>
            <h3>Example for Episodes</h3>
            <pre class="prettyprint">
"sourceFeed": {
  "description": "&amp;lt;p&amp;gt;&amp;lt;span style=\"font-size:12pt;\"&amp;gt;The Zyxx Fancast crew recaps Episode 113 of Mission to Zyxx, Dead Subquadrant's Got Talent. We talk about d12s. We discuss what Nermut's steam means. We steal a sweet URL. &amp;lt;br&amp;gt;&amp;lt;/span&amp;gt;&amp;lt;/p&amp;gt;\n&amp;lt;p&amp;gt;Hosts: Rebecca, Brandon, and Dariel&amp;lt;br&amp;gt;Editing: Brandon&amp;lt;br&amp;gt;Music by 8 Bit Jazz Heroes&amp;lt;br&amp;gt;Twitter: @ZyxxFancast",
  "episodeType": "full",
  "explicitLanguage": false,<br />  "guid": "42386318-a9d1-41f8-a10c-285f5d13281e",<br />  "imageUrl": "https://pbcdn1.podbean.com/imglogo/image-logo/4193270/Season2CoverArt2_smallerersquare.jpg",
  "websiteUrl": "https://zyxxfancast.podbean.com/e/zyxx-fancast-episode-113-w-special-guest-dariel/"<br />}</pre>
            <h3>Member Definition</h3>
            <table style="width: 100%;" class="TableStyle-Standard" cellspacing="0">
              <col style="width: 288px;" class="TableStyle-Standard-Column-Regular" />
              <col class="TableStyle-Standard-Column-Regular" />
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
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">author</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">The author of the feed.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">categories</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">Categories specified by the podcast publisher in the RSS feed.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">contentType</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">Indicates if the content is "Episodic" or "Serial", as defined by the publisher.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">copyright</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">Copyright information</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">description</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">Description of the podcast, as in the feed.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">episodeType</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">Full or partial episode.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">explicitLanguage</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">Boolean</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">Flag indicating if there may be explicit language in the content. </td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">feedURL</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">URL of the feed.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">generator</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">Feed generator.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">guid</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">The publisher-provided GUID.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">imageUrl</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">A graphic for use with the feed.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">owner</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">Owner of the feed.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">sourceFeed</td>
                  <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
                  <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing RSS data.</td>
                </tr>
                <tr class="TableStyle-Standard-Body-Row1">
                  <td class="TableStyle-Standard-BodyB-Regular-Row1">websiteUrl</td>
                  <td class="TableStyle-Standard-BodyB-Regular-Row1">string</td>
                  <td class="TableStyle-Standard-BodyA-Regular-Row1">
                    <span class="MCTextPopup">
                      <a class="MCTextPopupSpot_0">Series<img style="border: none;margin-left: 5px;" src="../SkinSupport/ExpandingClosed.gif" onload="if ( typeof( FMCPreloadImage ) == 'function' ) { FMCPreloadImage( '../SkinSupport/ExpandingOpen.gif' ); }" alt="Closed" class="MCExpandingIcon" /></a>
                      <span class="MCTextPopupBody_0">A continuing podcast that contains multiple individual segments.</span>
                    </span> official website as provided in the feed.</td>
                </tr>
              </tbody>
            </table>
            <p>
              <h2>series</h2>
              <p>
                <h3>Example</h3>
                <p>
                  <pre class="prettyprint">
"data": [
  {
    "categories": [
      [
        {
          "descriptorID": "90266",
          "display": "Education",
          "level": 1
	 },
	 {
          "descriptorID": "90321",
	   "display": "Learn Fun Stuff!",
	   "level": 2
	 }
      ],
      [
        {
          "descriptorID": "90274",<br />          "display": "Science",
          "level": 1
        }
      ],
      [
        {
          "descriptorID": "90275",
          "display": "Society &amp;amp; Culture",
          "level": 1
        },
        {
          "descriptorID": "90448",
          "display": "Culture",
          "level": 2
        }
      ]<br />    ],<br />    "country": null<br />    "avgEpisodeDurationSeconds": 2275,
    "credits": [
      {
        "name": "Jeremy Bent",
        "personID": "924899"<br />	"role": {
          "display": "Host"
	 }
      }
    ],
    "description": "An improvised science fiction sitcom following a team of ambassadors as they attempt to establish diplomatic relations with planets in the remote and chaotic Zyxx Quadrant… better known as the \"ass end of space.\"",
    "editorialStatus": "enhanced",
    "availabilities": [
      {
        "license": "Open",
        "name": "All"
      }
    ],<br />    "lastUpdateDateTime": "2020-08-24T02:56:12Z",<br />    "lastPublishDateTime": "2020-01-22T11:00:23Z",
    "numEpisodes": 72,
    "objectType": "series",
    "popularity": {</pre>
                  <pre class="prettyprint">      "global": 0.7,</pre>
                  <pre class="prettyprint">      "at": 0.6,<br />      "au": 0.3,<br />      "ca": 0.4,</pre>
                  <pre class="prettyprint">      "ch": 0.9,<br />      "de": 0.2,<br />      "es": 0.2,<br />      "fr": 0.1,<br />      "it": 0.4,</pre>
                  <pre class="prettyprint">      "kr": 0.1,<br />      "mx": 0.4,<br />      "uk": 0.6,
      "us": 0.8
    },
    "recommendedPodcastSeries": [
      "GA0000N000000WM",
      "GA0000N00000066",
      "GA0000N000000RZ"
    ],
    "sourceFeed": {
      "author": "Mission To Zyxx",
      "categories": [
        "Comedy",
        "Arts"
      ],
      "contentType": "Episodic",
      "copyright": "2017-2019 Zyxx Quadrant LLC",
      "description": "An improvised science fiction sitcom following a team of ambassadors as they attempt to establish diplomatic relations with planets in the remote and chaotic Zyxx Quadrant… better known as the \"ass end of space.\"",
      "explicitLanguage": true,
      "feedUrl": "https://feeds.simplecast.com/ZL7iUDiH",
      "generator": "https://simplecast.com",<br />      "imageUrl": "https://cdn.simplecast.com/images/fcda2e3-85e70/fcaf7fdb--23542a7/3000/mission_art.jpg?&amp;amp;aid=rss_feed",
      "owner": "Mission To Zyxx",
      "websiteUrl": "https://missiontozyxx.space/"
    },
    "seriesID": "GA0000N000000VH",<br />    "seriesRootID": "GA0001800010G4V",<br />    "subtitle": null,
    "summary": "An improvised science fiction sitcom following a team of ambassadors as they attempt to establish diplomatic relations with planets in the remote and chaotic Zyxx Quadrant… better known as the \"ass end of space.\"",
    "title": "Mission To Zyxx"
  }
]												
</pre> </p>
                <h3>Member Definition</h3>
                <table style="width: 100%;" class="TableStyle-Standard" cellspacing="0">
                  <col style="width: 288px;" class="TableStyle-Standard-Column-Regular" />
                  <col class="TableStyle-Standard-Column-Regular" />
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
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">availabilities</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">object </td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Availability of license.  See the section on <a href="#available" class="MCXref_0">availabilities</a> for more details.<td class="TableStyle-Standard-BodyE-Regular-Row1"></td></td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">avgEpisodeDurationSeconds</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">integer</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">The average duration of series episodes in seconds.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">categories</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">object </td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing category information for the episode. This object contains level one through three descriptor levels. See the section on <a href="#categori" class="MCXref_0">categories </a> for details.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">country</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Populated when there is a language defined as language + country. Most languages are available as 2-digit values like en while some are defined as en-US, en-AU.  The country field adds the country to the language, such as US English or Australian English. </td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">credits</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Credit objects for individuals present on the series. See the section on <a href="#credits" class="MCXref_0">credits</a> for details.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">data</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Object containing data.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">description</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Description of the series. </td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">editorialStatus</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">enum</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Status of the episode: "enhanced" to indicate a podcast with verified Gracenote-enhanced data and "original" to indicate a non verified podcast.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">lastPublishDateTime</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Date and time of the most recent episode of the series.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">lastUpdateDateTime</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Last update timestamp for the series in ISO 8601 format.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">numEpisodes</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">integer</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Number of episodes in the series.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">objectType</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Type of object.  Either episode or series.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">popularity</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">List of supported locales with popularity score attached. Scores are between 0.1 and 1 in increasing order of popularity.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">recommendedPodcastSeries</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">
                        <p>List of recommended series associated with current series. </p>
                      </td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">sourceFeed</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">object</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">RSS information for the series.  See the section on <a href="#sourceFeed" class="MCXref_0">sourceFeed</a> for more details.</td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">seriesID</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Gracenote unique ID code for the series. </td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">seriesRootID</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">Identifies a collection of similar series. Each series will have a seriesRootID and series that are variants of each other will share the same seriesRootID.  </td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">summary</td>
                      <td class="TableStyle-Standard-BodyE-Regular-Row1">string</td>
                      <td class="TableStyle-Standard-BodyD-Regular-Row1">
                        <span class="MCTextPopup">
                          <a class="MCTextPopupSpot_0">Summary<img style="border: none;margin-left: 5px;" src="../SkinSupport/ExpandingClosed.gif" onload="if ( typeof( FMCPreloadImage ) == 'function' ) { FMCPreloadImage( '../SkinSupport/ExpandingOpen.gif' ); }" alt="Closed" class="MCExpandingIcon" /></a>
                          <span class="MCTextPopupBody_0">A brief description of the contents of an episode.</span>
                        </span> of the series. </td>
                    </tr>
                    <tr class="TableStyle-Standard-Body-Row1">
                      <td class="TableStyle-Standard-BodyB-Regular-Row1">title</td>
                      <td class="TableStyle-Standard-BodyB-Regular-Row1">string</td>
                      <td class="TableStyle-Standard-BodyA-Regular-Row1">Title of the series.</td>
                    </tr>
                  </tbody>
                </table>
              </p>
            </p>
          </p>
        </p>
      </p>
    </p>
  </p>
</p>

<hr width="100%" size="0" align="center" />
