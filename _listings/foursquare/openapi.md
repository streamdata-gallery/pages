swagger: "2.0"
x-collection-name: Foursquare
x-complete: 1
info:
  title: Foursquare
  version: 1.0.0
host: api.foursquare.com
basePath: /v2/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /pages/search:
    get:
      summary: Get Pages Search
      description: /pages/{PAGE_ID}
      operationId: pagespage-id
      x-api-path-slug: pagessearch-get
      parameters:
      - in: query
        name: fbid
        description: A comma-delimited list of Facebook IDs to look for
      - in: query
        name: name
        description: A search term to be applied against page names
      - in: query
        name: twitter
        description: A comma-delimited list of Twitter handles to look for
      - in: query
        name: v
        description: All requests now accept a v=YYYYMMDD param, which indicates that
          the client is up to date as of the specified date
      responses:
        200:
          description: OK
      tags:
      - Pages
      - Search
  /pages/{PAGE_ID}:
    get:
      summary: Get Pages
      description: /events/search
      operationId: eventssearch
      x-api-path-slug: pagespage-id-get
      parameters:
      - in: query
        name: PAGE_ID
        description: Identity of the page to get details for
      - in: path
        name: PAGE_ID
      - in: query
        name: v
        description: All requests now accept a v=YYYYMMDD param, which indicates that
          the client is up to date as of the specified date
      responses:
        200:
          description: OK
      tags:
      - Pages
  /pages/{PAGE_ID}/venues:
    get:
      summary: Get Pages Venues
      description: /pages/search
      operationId: pagessearch
      x-api-path-slug: pagespage-idvenues-get
      parameters:
      - in: query
        name: limit
        description: The number of venues to return
      - in: query
        name: ll
        description: Not valid with ne or sw
      - in: query
        name: ne
        description: See sw
      - in: query
        name: offset
        description: The offset of which venues to return
      - in: query
        name: PAGE_ID
        description: The page id for which venues are being requested
      - in: path
        name: PAGE_ID
      - in: query
        name: radius
        description: Can be used when including ll
      - in: query
        name: sw
        description: With ne, limits results to the bounding quadrangle defined by
          the latitude and longitude given by sw as its south-west corner, and ne
          as its north-east corner
      - in: query
        name: v
        description: All requests now accept a v=YYYYMMDD param, which indicates that
          the client is up to date as of the specified date
      responses:
        200:
          description: OK
      tags:
      - Pages
      - Venues