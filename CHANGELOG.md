v1.4.3
------
* Clip buildings to tile boundaries. See #1142.
* Allow some kinds of non-numeric `shield_text`. See #1452.
* Add shops from osm.org and iD. See #1447.
* Clip buildings to tiles. See #1446.
* Include all name variants. See #1454.
* Add building material tag to output. See #1455.
* Add route modifier information to network. See #1460.
* Add wetland detail to kind_detail. See #1461.
* Remove unused wooded area tags + natural=park and add leaf_type to wooded areas. See #1459.
* Guard against TopologicalError. See #1471.

v1.4.1
------
* **Release date:** 2017-10-23.
* **Requires:** [tileserver v2.1.1](https://github.com/mapzen/tileserver/releases/tag/v2.1.1) and [tilequeue v1.8.1](https://github.com/mapzen/tilequeue/releases/tag/v1.8.1) and [mapbox-vector-tile v1.2.0](https://pypi.python.org/pypi/mapbox-vector-tile/v1.2.0).
* Backport fix for including VERSION file in package. See [#265](https://github.com/tilezen/vector-datasource/pull/1411).
* Point tilequeue/tileserver to specific versions in requirements.

v1.4.0-docs1
------
* **Release date**: 2017-06-28. _Live on prod 2017-06-??._
* **Requires:** [tileserver v2.1.0](https://github.com/mapzen/tileserver/releases/tag/v2.1.0) and [tilequeue v1.8.0](https://github.com/mapzen/tilequeue/releases/tag/v1.8.0) and [mapbox-vector-tile v1.2.0](https://pypi.python.org/pypi/mapbox-vector-tile/v1.2.0).
- [docs] Update link to pois.jinja2. See [#1268](https://github.com/tilezen/vector-datasource/pull/1268).
- [docs] Update `your-mapzen-api-key` URL query strings to enable key substitution. See [#1275](https://github.com/tilezen/vector-datasource/pull/1275).
- [docs] Spelling, grammar, writing style fixes. See [#1275](https://github.com/tilezen/vector-datasource/pull/1275).
- [docs] Add documentation for 512 pixel tile sizes. See [#1284](https://github.com/tilezen/vector-datasource/pull/1284).
- [docs] Add documentation to suggest max zoom (per tile size). See [#1161](https://github.com/tilezen/vector-datasource/pull/1161).
- [docs] Add documentation for tile x, y coordinates (versus latitude and longitude). See [#1111](https://github.com/tilezen/vector-datasource/pull/1111).
- [docs] Add documentation for HTTP status codes. See [#1266](https://github.com/tilezen/vector-datasource/pull/1266).
- [tests] Update tests for upstream OpenStreetMap data churn. See [#1267](https://github.com/tilezen/vector-datasource/pull/1267), [#1282](https://github.com/tilezen/vector-datasource/pull/1282), and [#1286](https://github.com/tilezen/vector-datasource/pull/1286).
- Remove duplicate symbol output. See [#1265](https://github.com/tilezen/vector-datasource/pull/1265).
- Fixed release notes on 2017-07-19 with corrected **Requires** section.

v1.4.0
------
* **Release date**: 2017-05-31.
* **Requires:** [tileserver v2.1.0](https://github.com/mapzen/tileserver/releases/tag/v2.1.0) and [tilequeue v1.8.0](https://github.com/mapzen/tilequeue/releases/tag/v1.8.0) and [mapbox-vector-tile v1.2.0](https://pypi.python.org/pypi/mapbox-vector-tile/v1.2.0).
- [tests] Add support to capture all test coordinates with `-printcoords`. This also namespaces all the test assertion functions using `test`. See [#1245](https://github.com/tilezen/vector-datasource/issues/1245).
- [tests] Publish all test coordinates for master CircleCI builds. See [#1246](https://github.com/tilezen/vector-datasource/pull/1246).
- [docs] Remove rate limiting note (for Mapzen hosted service).

v1.3.0-docs1
------
* **Release date**: 2017-05-05.
* **Requires:** [tileserver v2.0.0](https://github.com/mapzen/tileserver/releases/tag/v2.0.0) and [tilequeue v1.7.0](https://github.com/mapzen/tilequeue/releases/tag/v1.7.0) and [mapbox-vector-tile v1.2.0](https://pypi.python.org/pypi/mapbox-vector-tile/v1.2.0).
- [docs] Delete api-keys-and-rate-limits.md page
- [docs] Update attribution.md page with less Mapzen
- [docs] Add `your_mapzen_api_key` URL query strings to URL endpoint examples
- [changelog] Update mapbox-vector-tile pypi urls
- [tests] island > islet for OSM data change

v1.3.0
------
* **Release date**: 2017-05-04. _Live on prod 2017-05-08._
* **Requires:** [tileserver v2.0.0](https://github.com/mapzen/tileserver/releases/tag/v2.0.0) and [tilequeue v1.7.0](https://github.com/mapzen/tilequeue/releases/tag/v1.7.0) and [mapbox-vector-tile v1.2.0](https://pypi.python.org/pypi/mapbox-vector-tile/1.2.0).

  #### ENHANCEMENTS

  * Show important cycling and walking routes at earlier zooms by adjusting the `min_zoom` of `path`, `major_road`, and `minor_road` cycling and walking related features in the **roads** layer. This means that `min_zoom` values are now variable for features of the same kind, depending on their importance in the bicycle and walking networks; in earlier releases they all shared the same `min_zoom`. See [#1172](https://github.com/tilezen/vector-datasource/issues/1172).
  * Add shields for bicycle, walking, and bus networks with new `bicycle_network`, `walking_network`, `bus_network`, `bicycle_shield_text`, `walking_shield_text`, `bus_shield_text`, and `all_*` variants onto **road** layer features. See [#775](https://github.com/tilezen/vector-datasource/issues/775), [#1175](https://github.com/tilezen/vector-datasource/issues/1175), and [#1214](https://github.com/tilezen/vector-datasource/issues/1214).
  * Add `bicycle` property to non-path **road** layer features to more accurately reflect `is_bicycle_related` routes (eg for ways tagged `bicycle=designated`). See [#1171](https://github.com/tilezen/vector-datasource/issues/1171).
  * Add `surface` property to **roads** layer features. See [#1020](https://github.com/tilezen/vector-datasource/issues/1020).
  * Add `ramp` and `ramp_bicycle` property to **roads** layer features. See  [#1147](https://github.com/tilezen/vector-datasource/issues/1147).
  * Remove `motor_vehicle`, `horse` and some other properties at low- and mid-zooms in **roads** layer. See [#1224](https://github.com/tilezen/vector-datasource/issues/1224) and [#1214](https://github.com/tilezen/vector-datasource/issues/1214).
  * Improve line merging in **roads** and other layers to reduce tile file size and improve rendering performance. See [#1191](https://github.com/tilezen/vector-datasource/issues/1191).
  * Add `colour_name` property for **transit** layer features. See [#1190](https://github.com/tilezen/vector-datasource/issues/1190).
  * Show large piers earlier in **landuse** layer. See [#1178](https://github.com/tilezen/vector-datasource/issues/1178).
  * Remove many **pois** layer features when they lack a name (but many others are whitelisted as no-name okay). See [#1186](https://github.com/tilezen/vector-datasource/issues/1186) and [#1218](https://github.com/tilezen/vector-datasource/issues/1218).

  #### BUG FIXES

  * Fix spelling of ~60 locality (city) names at low-zooms in **places** layer. [#1140](https://github.com/tilezen/vector-datasource/issues/1140).
  * Small gardens (in Edinburgh and elsewhere) should not be visible at mid-zooms in **pois** layer. [#1185](https://github.com/tilezen/vector-datasource/issues/1185).
  * Some **pois** layer features were missing their `tier` property. See [#1208](https://github.com/tilezen/vector-datasource/issues/1208).
  * Remove `natural_forest`, `natural_wood`, and `village_green` from **pois** layer, a documented breaking bug fix associated with the v1.0 release. Their label points are now found in the **landuse** layer. See [#1103](https://github.com/tilezen/vector-datasource/issues/1103).
  * Fix test failures based on upstream OpenStreetMap data changes.
  * _NOTE: while the v1.3.0 release was tagged correctly the VERSION file was stuck at v1.2.0 leading to the incorrectly report in Python installs as v1.2.0._

  

v1.2.0
------
* **Release date**: 2017-03-23. _Live on prod 2017-03-27._
* **Requires:** [tileserver v1.4.0](https://github.com/mapzen/tileserver/releases/tag/v1.4.0) and [tilequeue v1.6.0](https://github.com/mapzen/tilequeue/releases/tag/v1.6.0) and [mapbox-vector-tile v1.2.0](https://pypi.python.org/pypi/mapbox-vector-tile/1.2.0).
* Generate less-complex MultiPolygons by limiting the number of features that can be merged into a single MultiPolygon (defaults to 1000). This can have a large impact on geometric topology checks for file formats like MVT. See [#1176](https://github.com/tilezen/vector-datasource/pull/1176).
* Move merging of landuse polygons after roads intercut, to improve intercut performance. See [#1177]( https://github.com/tilezen/vector-datasource/pull/1177).
* Drop small inner polygons, to improve downstream performance. See [#1180](https://github.com/tilezen/vector-datasource/pull/1180).
* Fix test failures based on OpenStreetMap data changes and 2x2 metatiles where unit of work for some operations like `tile_kind_rank` is now 512px instead of 256px. See [#1182](https://github.com/tilezen/vector-datasource/pull/1182).

v1.1.0
------
* **Release date**: 2017-02-17.
* **Requires:** [tileserver v1.3.0](https://github.com/mapzen/tileserver/releases/tag/v1.3.0) and [tilequeue v1.4.0](https://github.com/mapzen/tilequeue/releases/tag/v1.4.0) and [mapbox-vector-tile v1.1.0](https://pypi.python.org/pypi/mapbox-vector-tile/1.1.0).
* Replace usage of tile coordinate with usage of nominal zoom. (See https://github.com/tilezen/vector-datasource/pull/1166)

v1.0.3
------
* **Release date**: 2017-01-24.
* **Requires:** [tileserver v1.1.0](https://github.com/mapzen/tileserver/releases/tag/v1.1.0) and [tilequeue v1.2.0](https://github.com/mapzen/tilequeue/releases/tag/v1.2.0) and [mapbox-vector-tile v1.0.0](https://pypi.python.org/pypi/mapbox-vector-tile/1.0.0).
* Clarify documentation license as CC-BY. See [#1136](https://github.com/tilezen/vector-datasource/issues/1136).
* Fix test failures. See [#1148](https://github.com/tilezen/vector-datasource/issues/1148), [#1150](https://github.com/tilezen/vector-datasource/pull/1150), [#1152](https://github.com/tilezen/vector-datasource/pull/1152), [#1157](https://github.com/tilezen/vector-datasource/pull/1157).


v1.0.2
------
* **Release date**: 2016-11-17. _Live on prod 2016-11-21._
* **Requires:** [tileserver v1.0.0](https://github.com/mapzen/tileserver/releases/tag/v1.0.0) and [tilequeue v1.0.1](https://github.com/mapzen/tilequeue/releases/tag/v1.0.1) and [mapbox-vector-tile v1.0.0](https://pypi.python.org/pypi/mapbox-vector-tile/1.0.0).
* Merge water and earth polygons. See [#1106](https://github.com/tilezen/vector-datasource/issues/1106).
* Improve maritime_boundary tagging in Europe and globally by updating buffered_land shapefile. See [#294](https://github.com/tilezen/vector-datasource/issues/294).

v1.0.1
------
* **Release date**: 2016-11-04. _Live on prod 2016-11-04._
* **Requires:** [tileserver v1.0.0](https://github.com/mapzen/tileserver/releases/tag/v1.0.0) and [tilequeue v1.0.1](https://github.com/mapzen/tilequeue/releases/tag/v1.0.1) and [mapbox-vector-tile v1.0.0](https://pypi.python.org/pypi/mapbox-vector-tile/1.0.0).
* Update boundaries query to use overlaps filter to improve performance.

v1.0.0
------
* **Release date**: 2016-10-04. _Live on prod 2016-10-13._
* **Requires:** [tileserver v1.0.0](https://github.com/mapzen/tileserver/releases/tag/v1.0.0) and [tilequeue v1.0.0](https://github.com/mapzen/tilequeue/releases/tag/v1.0.0) and [mapbox-vector-tile v1.0.0](https://pypi.python.org/pypi/mapbox-vector-tile/1.0.0).

---

* **New production URLs:**
    * **GeoJSON:**
      `http://tile.mapzen.com/mapzen/vector/v1/all/{z}/{x}/{y}.json?api_key=mapzen-xxxxxxx`
    * **TopoJSON:**
      `http://tile.mapzen.com/mapzen/vector/v1/all/{z}/{x}/{y}.topojson?api_key=mapzen-xxxxxxx`
    * **Mapbox Vector Tile:**
      `http://tile.mapzen.com/mapzen/vector/v1/all/{z}/{x}/{y}.mvt?api_key=mapzen-xxxxxxx`

---

* Guard against intersecting with same ids during admin boundary processing.
* Rank only features within the unpadded bounds of the tile. Drop unranked features within the unpadded bounds.
* Drop linear boundaries (preferring relation boundaries only), as linear boundaries break the admin boundary processing code.
* Add pyclipper dependency to requirements.
* Include name:short as a tag name alternate.
* Fixed bug to restore some missing low-zoom region boundary lines.
* Fixed bug to fully enable new map_unit boundary lines at low-zooms.
* Low-zoom boundary lines now have custom min_zoom values.
* All features in place layer now have custom min_zoom values.
* Update data query to adapt to upstream OpenStreetMap healthcare speciality bulk edit.
* Fixed typo for protction_title to protection_title for National Forest features in pois layers.
* [docs] Cleanup docs generally, clarify relationship between pois and landuse layers, and remove promise about tier property (which will probably be deprecated).
* [docs] Migrate docs to reference generic Mapzen API keys.


v1.0.0-pre3
-------

* **Release date**: 2016-09-16 (dev build only as public preview)
* **Requires:** [tileserver v0.8.0-pre2](https://github.com/mapzen/tileserver/releases/tag/v0.8.0-pre2) and [tilequeue v0.11.0-pre2](https://github.com/mapzen/tilequeue/releases/tag/v0.11.0-pre2) and [mapbox-vector-tile v0.5.0](https://pypi.python.org/pypi/mapbox-vector-tile/0.5.0).

---

* **Developer preview URLs:** API endpoints have generalized for multiple tile sets, accounts, and versions:
    * **GeoJSON:** http://tile.dev.mapzen.com/mapzen/vector/v1/all/{z}/{x}/{y}.json
    * **TopoJSON:** http://tile.dev.mapzen.com/mapzen/vector/v1/all/{z}/{x}/{y}.topojson
    * **Mapbox Vector Tile:** http://tile.dev.mapzen.com/mapzen/vector/v1/all/{z}/{x}/{y}.mvt
* **Production URLs will be (not yet live):**
    * **GeoJSON:** http://tile.mapzen.com/mapzen/vector/v1/all/{z}/{x}/{y}.json
    * **TopoJSON:** http://tile.mapzen.com/mapzen/vector/v1/all/{z}/{x}/{y}.topojson
    * **Mapbox Vector Tile:** http://tile.mapzen.com/mapzen/vector/v1/all/{z}/{x}/{y}.mvt

---

* Removed "not equals" YAML rule, which can be expressed using the other "equals" and "not" operators. [PR #1044](https://github.com/tilezen/vector-datasource/pull/1044).
* **BREAKING** Rename `sort_key` to `sort_rank`. [PR #1049](https://github.com/tilezen/vector-datasource/pull/1049).
* **BREAKING** Add `/mapzen` prefix to tilejson tiles URL. [PR #1047](https://github.com/tilezen/vector-datasource/pull/1047).
* New version of "static" Natural Earth and OSM shapefiles. [PR #1046](https://github.com/tilezen/vector-datasource/pull/1046).
* Restore buildings to zoom 13. [PR #1036](https://github.com/tilezen/vector-datasource/pull/1036).
* **BREAKING** Fix scalerank 0 region boundaries. Drop name properties on boundaries at zoom <= 6. Add region boundaries sourced from Natural Earth "map_unit" data. [PR #1037](https://github.com/tilezen/vector-datasource/pull/1037).
* Add `min_zoom` parameter to all features. [PR #1031](https://github.com/tilezen/vector-datasource/pull/1031).
* Allow null refs in shield text. Attempt to sanitize shield text by omitting leading text such as `A` or `M` before numeric references. [PR #1039](https://github.com/tilezen/vector-datasource/pull/1039).
* **BREAKING** Update Natural Earth road properties. Removes `level`, `namealt` and `namealtt`. Adds `network` and `shield_text` for some countries. [PR #1035](https://github.com/tilezen/vector-datasource/pull/1035).
* **BREAKING** Fix filters for national forests and parks. Features are now required to have additional parameters (e.g: `operator`, `protect_class`, ...) to classify as a `kind: national_park`. [PR #1034](https://github.com/tilezen/vector-datasource/pull/1034).
* Fix missing localized names on boundaries. Boundaries now include localized `name:left:*` and `name:right:*` where the data is available. [PR #1022](https://github.com/tilezen/vector-datasource/pull/1022).
* Change min zoom for landuse, POIs to be closer to Bubble Wrap. Adds `tier` parameter to simplify client-side rendering rules. [PR #997](https://github.com/tilezen/vector-datasource/pull/997).

v1.0.0-pre2
-------
* **Release date**: 2016-08-31 (dev build only as public preview)
* See detailed Breaking changes, New features, Bug fixes, and Internal Changes sections below.
* **Requires:** [tileserver v0.8.0-pre2](https://github.com/mapzen/tileserver/releases/tag/v0.8.0-pre2) and [tilequeue v0.11.0-pre2](https://github.com/mapzen/tilequeue/releases/tag/v0.11.0-pre2)

  #### BREAKING CHANGES (v1.0.0-pre2)

- **all** layers: Revert to 2 letter language codes to remove client 3-char to 2-char shim logic, with better fallbacks. ([#972](https://github.com/tilezen/vector-datasource/issues/972))

- **boundaries**, **places**, and **roads** layers: Remove raw Natural Earth `scalerank` (see `min_zoom` instead) and `labelrank` properties. ([#992](https://github.com/tilezen/vector-datasource/issues/992))

- **buildings** layer: remove label placements from low- and mid-zooms, keep at zoom 16+. ([#679](https://github.com/tilezen/vector-datasource/issues/679))

- **landuse** layer: Low- and mid-zoom landuse polygons are now merged within the same `kind` values to significantly reduce file size. Some properties, like `name`, `id`, `sport`, `religion`, and `surface` are dropped, and the `area` is recalculated for new combo polygons. [Planned work](https://github.com/tilezen/vector-datasource/issues/473) will add back some detail by adding `scale_rank` classes pre-merge (matching **buildings** layer behavior). ([#583](https://github.com/tilezen/vector-datasource/issues/583))

- **landuse** layer: Remove label placements for `cemetery`, `farm`, `forest`, `forest`, `golf_course`, `grave_yard`, `military`, `national_park`, `natural_forest`, `natural_wood`, `nature_reserve`, `park`, `pitch`, `plant`, `protected_area`, `quarry`, `recreation_ground`, `substation`, `village_green`, `wastewater_plant`, `water_works`, `winter_sports`, `wood`, `works` features, moving them to **pois** layer. Remaining label placements are recommended for text only label treatment.([#742](https://github.com/tilezen/vector-datasource/issues/742))

- **landuse** layer: remove label placements from low- and mid-zooms, keep at zoom 15+. ([#679](https://github.com/tilezen/vector-datasource/issues/679))

- **places** layer: Additional locality changes for places layer to normalize place layer kinds: `capital` changes to `country_capital`, `state_capital` changes to `region_capital`, `scientific_station` localities get their own `kind_detail`, and other bug fixes for ([#840](https://github.com/tilezen/vector-datasource/issues/840)). ([#931](https://github.com/tilezen/vector-datasource/issues/931))

- **pois** layer: Remove the `cuisine` property (see new `kind_detail` instead). ([#719](https://github.com/tilezen/vector-datasource/issues/719))

- **pois** layer: Modify default min_zoom for `gate` features. Gates on major roads are now visible at zoom 14, gates on intermediate roads at zoom 15, gates on minor roads at zoom 16, and gates not on roads at zoom 17 (was all zoom 15). ([#820](https://github.com/tilezen/vector-datasource/issues/820))

- **roads** layer: Remove `aerialway`, `highway`, `piste_type`, `railway`,  in favor of coalescing their values into a new `kind_detail` property (and change incorrect `subkind` reference in documentation to `kind_detail`). ([#970](https://github.com/tilezen/vector-datasource/issues/970))

- **transit** layer: rename `root_relation_id` property to `root_id`, matching new **building** layer configuration. ([#969](https://github.com/tilezen/vector-datasource/pull/969) and [#653](https://github.com/tilezen/vector-datasource/issues/653))

- **water** layer: Remove duplicative and poor resolution `sea` polygons (but keep their label centroids) to save Venice and other cities from early global warming! This also addressed excessive sea labels in most Mapzen house styles. ([#951](https://github.com/tilezen/vector-datasource/issues/951))

  #### NEW FEATURES (v1.0.0-pre2)

- **tilejson**: Major upgrade to reflect all layers and properties. ([#938](https://github.com/tilezen/vector-datasource/issues/938))

- **versioning**: Add semantic versioning (semver) document detailing the promises Tilezen makes about major, minor, and patch versions and data model changes. ([#948](https://github.com/tilezen/vector-datasource/issues/948))

- **buildings** layer: Building parts may receive a `root_id` corresponding to the building feature, if any, with which they intersect. ([#653](https://github.com/tilezen/vector-datasource/issues/653))

- **landuse** layer: Add `graveyard` features. ([#742](https://github.com/tilezen/vector-datasource/issues/742))

- **landuse** layer: Add `camp_site` features for camp grounds. ([#875](https://github.com/tilezen/vector-datasource/issues/875))

- **pois** layer: Add `cemetery`, `farm`, `forest`, `forest`, `golf_course`, `military`, `national_park`, `natural_forest`, `natural_wood`, `nature_reserve`, `park`, `pitch`, `plant`, `protected_area`, `quarry`, `recreation_ground`, `substation`, `village_green`, `wastewater_plant`, `water_works`, `winter_sports`, `wood`, `works` features with adjusted zoom ranges over their previous availability in the **landuse** layer as label placements. All remaining label placements in the **landuse** layer are no longer recommended for icon label treatment. ([#742](https://github.com/tilezen/vector-datasource/issues/742))

- **pois** layer: Add `graveyard` features. ([#742](https://github.com/tilezen/vector-datasource/issues/742))

- **pois** layer: Add art `gallery` features. ([#990](https://github.com/tilezen/vector-datasource/issues/990))

- **pois** layer: Add `kind_detail` property sourced from `sport` for `pitch` features and sourced from `cuisine` for `biergarten`, `pub`, `bar`, `restaurant`, `fast_food`, `cafe` kinds (removing the `cuisine` property). ([#719](https://github.com/tilezen/vector-datasource/issues/719))

- **roads** layer: To support highway shields a new `shield_text` property has been added, `network` values have been normalized (and bicycle networks are now excluded). An example: for "US 101" we now store `network` of  **US:US** and `shield_text` of **101**. Multiple shields are supported via optional `all_networks` and `all_shield_texts` lists (which work in GeoJSON and TopoJSON but not MVT formats, follow [mapbox-vector-tile/#64](https://github.com/tilezen/mapbox-vector-tile/issues/64) for a fix). The `ref` property remains available but is less useful for shield construction. ([#192](https://github.com/tilezen/vector-datasource/issues/192) and [#896](https://github.com/tilezen/vector-datasource/issues/896))

  #### BUG FIXES (v1.0.0-pre2)

- **all** layers: Support fractional zoom for POIs, places, and other featues which were only appearing at the next whole integer tile, and rounds min_zoom values to 2 decimal places. For example: a feature with `min_zoom` of **14.8** was only appearing in zoom **15** tiles when it should have appeared in the zoom **14** tile. ([#976](https://github.com/tilezen/vector-datasource/issues/976))

- **boundaries** layer: Correct bug where `sort_key` mapping wasn't updated for new boundary `kind` values from v1.0.0-pre1. ([#1012](https://github.com/tilezen/vector-datasource/issues/1012))

- **places** layer: Adjust default zoom ranges for Natural Earth localities at the low-zooms and Natural Earth and OpenStreetMap localities at mid- and high-zooms. ([#981](https://github.com/tilezen/vector-datasource/issues/981) and [#982](https://github.com/tilezen/vector-datasource/issues/982))

- **places** layer: Exclude `region_capital=false` properties. ([#1003](https://github.com/tilezen/vector-datasource/pull/1003) and [#931](https://github.com/tilezen/vector-datasource/issues/931))

- **pois** layer: Add OpenStreetMap `source` attribution per feature. ([#922](https://github.com/tilezen/vector-datasource/issues/922))

- **pois** layer: Start querying for pois at z4, not z2 (matching the **landuse** layer). ([#994](https://github.com/tilezen/vector-datasource/pull/994))

- **pois** layer: Show large `camp_site` features at earlier zooms. ([#875](https://github.com/tilezen/vector-datasource/issues/875))

- **pois** layer: Removed transit `halt`, `station`, `stop`, and `tram_stop` features marked as historic. ([#661](https://github.com/tilezen/vector-datasource/issues/661))

- **pois** and **landuse** layers: Normalize `operator` values for `United States National Park Service`, `United States Forest Service`, and `National Parks & WildlWildlifeife Service NSW` in the U.S.A. and Australia. ([#927](https://github.com/tilezen/vector-datasource/issues/927))

- **roads** layer: Pedestrian paths and piers were missing `bicycle: designated` and related tags. Now that they are exported, they are correctly also decorated as `is_bicycle_related: True`. ([#832](https://github.com/tilezen/vector-datasource/issues/832))

- **roads** layer: Add additional properties `sidewalk_left` and `sidewalk_right` to all road layer features. ([#605](https://github.com/tilezen/vector-datasource/issues/605) and [#986](https://github.com/tilezen/vector-datasource/issues/986))

- **roads** layer: Remove `crossing`, `sidewalk`, `sidewalk_left` and `sidewalk_right` properties for road merge. ([#993](https://github.com/tilezen/vector-datasource/issues/993))

- **roads** layer: Drop meaningless `id` property on merged features. ([#952](https://github.com/tilezen/vector-datasource/issues/952))

- **transit** layer: Add OpenStreetMap `source` attribution per feature. ([#935](https://github.com/tilezen/vector-datasource/issues/935))

  #### DOCUMENTATION CHANGES (v1.0.0-pre2)

- **documentation**: Update **earth** layer documentation to reflect additional `line` and `point` geometry types. ([#808](https://github.com/tilezen/vector-datasource/issues/808))

- **documentation**: Update **boundaries** and **landuse** layer documentation to reflect barriers moving into the landuse layer. ([#932](https://github.com/tilezen/vector-datasource/issues/932))

- **documentation**: Update **places** layer documentation to reflect new `kind` and `kind_detail` values, locality, suburb, quarter, state, province, region, capital, and other changes. ([#934](https://github.com/tilezen/vector-datasource/issues/934))

- **documentation**: Update **buildings** layer documentation to reflect new `kind` and `kind_detail` values and `building_part` changes. ([#933](https://github.com/tilezen/vector-datasource/issues/933)) and related ([#842](https://github.com/tilezen/vector-datasource/issues/842))

- **documentation**: Update **roads** layer documentation to reflect new `kind` and `kind_detail` values, and remove erroneous reference to `exit`. ([#936](https://github.com/tilezen/vector-datasource/issues/936))

- **contributing**: Adding a step to create a `test_config.yaml` file. ([#1001](https://github.com/tilezen/vector-datasource/pull/1001))


  #### INTERNAL CHANGES (v1.0.0-pre2)

- **performance**: Move label centroid calculation to database to reduce network pressure on the database (post processing transform needed too much geometry) in **landuse**, **water**, **earth**, and **buildings** layers. ([#965](https://github.com/tilezen/vector-datasource/issues/965))

- **performance**: Add pois indexes for OpenStreetMap polygon and point tables to improve query time. ([#983](https://github.com/tilezen/vector-datasource/issues/983))

- **database**: Convert Postgres PostGIS database to utilize osm2pgsql's `--hstore-all` option. ([#876](https://github.com/tilezen/vector-datasource/issues/876))

- **database**: Convert Postgres PostGIS database projection to `EPSG:3857`. ([#908](https://github.com/tilezen/vector-datasource/issues/908))

- **database**: Convert `min_zoom` properties to REAL from INT to support fractional values. ([#976](https://github.com/tilezen/vector-datasource/issues/976))

- **import**: Remove default `-W UTF-8` from data import config for shp2pgsql. ([#946](https://github.com/tilezen/vector-datasource/issues/946))

- **import**: Add shim in apply non planet sql to better accommodate invalid geometries. Track longer term fix in #979. ([#1003](https://github.com/tilezen/vector-datasource/pull/1003))

- **indexes**: Update road indexes to refer to `mz_road_level` alone. ([#956](https://github.com/tilezen/vector-datasource/pull/956))

- **tests**: Correct test failure for hotels as upstream data had changed. ([#959](https://github.com/tilezen/vector-datasource/pull/959))

- **tests**: Ensure that when `config_all_layers` is set, the **all** layer is requested. ([#974](https://github.com/tilezen/vector-datasource/pull/974))


v1.0.0-pre1
-------
* **Release date**: 2016-07-22 (dev build only as public preview)
* See detailed Breaking changes, New features, Bug fixes, and Internal Changes sections below.
* **Requires:** [tileserver v0.8.0.dev0](https://github.com/mapzen/tileserver/releases/tag/v0.8.0.dev0) and [tilequeue v0.11.0.dev0](https://github.com/mapzen/tilequeue/releases/tag/v0.11.0.dev0)

  #### BREAKING CHANGES (v1.0.0-pre1)

- **new url scheme**: Mapzen now offers several different types of tiles in vector and raster formats and we combine data from multiple sources. The URL scheme has been updated to reflect this, and emphasize versions. The old URL will continue to work (~1 year), but updates will stop once v1.0.0 is released to production. ([#652](https://github.com/tilezen/vector-datasource/issues/652))

  - **New dev URL:** `http://tile.dev.mapzen.com/vector/v1/all/{z}/{x}/{y}.topojson`

  - Old dev URL was: `http://vector.dev.mapzen.com/osm/all/{z}/{x}/{y}.topojson`

  - **New prod URL will be:** `https://tile.mapzen.com/vector/v1/all/{z}/{x}/{y}.topojson`

  - Old prod URL is still: `https://vector.mapzen.com/osm/all/{z}/{x}/{y}.topojson`

  - **New dev TileJSON is:** `http://tile.dev.mapzen.com/vector/v1/tilejson/mapbox.json`

  - New prod TileJSON will be: `https://tile.mapzen.com/vector/v1/tilejson/mapbox.json`

  - Old prod TileJSON is still: `https://vector.mapzen.com/osm/tilejson/mapbox.json`

- **roads** layer: Reclassify airport runway and taxiways as new `aeroway` kind (was `minor_road`), and change their sort order to be under equivalent landuse polygons. ([#895](https://github.com/tilezen/vector-datasource/issues/895))

- **roads** layer: Reclassify road layer kind values sourced from Natural Earth to use OpenStreetMap style kind values. ([#890](https://github.com/tilezen/vector-datasource/issues/890))

- **roads** layer: Normalize several kind values to remove `-` and replace with `_`, including `drive_through`, `j_bar`, and `t_bar`. ([#843](https://github.com/tilezen/vector-datasource/issues/843))

- **boundaries** layer: Reclassify boundary layer `kind` values for some OpenStreetMap, including `region` (was `state`), `locality` (was `municipality`), and many country related kind changes from Natural Earth at low zooms. ([#841](https://github.com/tilezen/vector-datasource/issues/841))

- **places** layer: Normalize place layer kinds coming from OpenStreetMap and Natural Earth to more closely match Who's On First (mostly using `locality` kind, with new `kind_detail` storing the original OSM and NE values). See this [lookup table](https://github.com/tilezen/vector-datasource/blob/master/yaml/places.yaml) for details. ([#840](https://github.com/tilezen/vector-datasource/issues/840))

- **places** layer: Remove country labels from zoom 0, 1 to reduce tile file size. ([#837](https://github.com/tilezen/vector-datasource/issues/837))

- **places** layer: Remove some types of OpenStreetMap neighbourhoods (`borough`, `suburb`, and `quarter`) in favor of Who's On First neighbourhoods. ([#744](https://github.com/tilezen/vector-datasource/issues/744))

- **pois** layer: Rename several kinds to distinguish `aeroway_gate` from `gate`, specify `gas_canister` shops (was `gas` which was confusing with automotive gas stations), and split off `ski_rental` if a `ski` feature was primarily a rental facility. ([#844](https://github.com/tilezen/vector-datasource/issues/844))

- **landuse** layer: Rename several kinds to distinguish `natural_wood` from `wood` parks, `natural_forest` from `forest` parks, and `natural_park` from `natural` parks. ([#844](https://github.com/tilezen/vector-datasource/issues/844))

- **transit** layer: `route_name` on line geometries is now simply `name`. ([#729](https://github.com/tilezen/vector-datasource/issues/729))

- **landuse** layer: Normalize `urban_area` landuse kinds from Natural Earth (was `urban area`). ([#713](https://github.com/tilezen/vector-datasource/issues/713))

- **landuse** and **boundaries** layers: Move barrier lines from boundaries layer into landuse layer. Includes `city_wall`, `dam`, `fence`, `retaining_wall`, and `snow_fence`. Watch out for `dam` which is now both a polygon and line in the same landuse layer. ([#857](https://github.com/tilezen/vector-datasource/issues/857))

- **buildings** layer: Reclassify building layer kind values to only have `building` or `building_part`, moved the earlier kind values to new `kind_detail` property with a whitelist of values. ([#842](https://github.com/tilezen/vector-datasource/issues/842))

- **buildings** layer: Reduce building payloads by merging buildings of similar type at zooms 13, 14, and 15 by dropping some properties like `name`, `addr_housenumber`, and `addr_street`, and quantizing others like `height` to 10 meters (zoom 13), 5 meters (zoom 14), and nearest meter (zoom 15). Also added new `scalerank` property with large buildings at 1 and small buildings at 5 to improve client-side style filtering & draw performance. ([#845](https://github.com/tilezen/vector-datasource/issues/845))

- Remove **landuse-labels** layer in favor of label placements in `landuse` layer and `pois` features. ([#852](https://github.com/tilezen/vector-datasource/issues/852))

- Use boolean values instead of 'yes' for properties like`osm_relation` and `label_placement`. ([#778](https://github.com/tilezen/vector-datasource/issues/778))

- Names that have been localized now use the _l10n_ language codes (ala Who's On First) for all data sources. For example: `name:en` imported from OpenStreetMap is exported as `name:eng`. ([#418](https://github.com/tilezen/vector-datasource/issues/418))


  #### NEW FEATURES (v1.0.0-pre1)

- **roads** layer: Add racetracks as type of `minor_road` sourced from OpenStreetMap's `highway=raceway`. See  [#664](https://github.com/tilezen/vector-datasource/issues/664))

- **roads** layer: Add indoor corridors as type of `path` sourced from OpenStreetMap's `highway=corridor`. ([#605](https://github.com/tilezen/vector-datasource/issues/605))

- **roads** layer: Add properties for `crossing=*`, `sidewalk=*` to all road layer features. ([#605](https://github.com/tilezen/vector-datasource/issues/605))

- **roads** layer: Add `bridleway` as type of `path`. ([#859](https://github.com/tilezen/vector-datasource/issues/859))

- **pois** layer: Add `toll_booth` sourced from OpenStreetMap's `barrier=toll_booth`. ([#479](https://github.com/tilezen/vector-datasource/issues/479))

- **pois** and **landuse** layers: Add `rest_area` and `service_area` kinds sourced from OpenStreetMap's `highway=rest_area` and `highway=services`. ([#480](https://github.com/tilezen/vector-datasource/issues/480))

- **places** layer: Add localized names for Who's On First sourced neighbourhoods using _l10n_ conventions. ([#418](https://github.com/tilezen/vector-datasource/issues/418))

- **places** layer: Add `borough` features from Who's On First (e.g.: Manhattan in New York City). ([#654](https://github.com/tilezen/vector-datasource/issues/654))



  #### BUG FIXES (v1.0.0-pre1)

- **pois** layer: Some walking network points were wrongly classified as `rwn` when they were actually `iwn`. ([#844](https://github.com/tilezen/vector-datasource/issues/844))

- **pois** and **landuse** layers: `garden` kind should win over `attraction`, and add garden point geometries (was previously limited to polygon features). ([#829](https://github.com/tilezen/vector-datasource/issues/829))

- **pois** layer: Show `windmill` features earlier, especially if they are a tourist attraction. ([#830](https://github.com/tilezen/vector-datasource/issues/830))

- **pois** layer: Show `lighthouse` features earlier, especially if they are a tourist attraction, as lighthouses. ([#860](https://github.com/tilezen/vector-datasource/issues/860))

- **pois** layer: Show camp grounds (`camp_site`) earlier. ([#875](https://github.com/tilezen/vector-datasource/issues/875))

- Update JSON encoding to handle invalid geometries (use the python `round` function), improves but does not completely solve invalid geometries in other formats like MVT. ([#698](https://github.com/tilezen/vector-datasource/issues/698))

- Drop all internal properties with a custom `mz` prefix, affected `mz_is_building` in **landuse** layer, but could have affected more layers. ([#622](https://github.com/tilezen/vector-datasource/issues/622))



  #### INTERNAL CHANGES (v1.0.0-pre1)

- **pois** layer: Remove several redundant filters for `boat_storage`, `firepit`, `dry_cleaning`, `toilets`, `theatre`, and `picnic_site`. ([#844](https://github.com/tilezen/vector-datasource/issues/844))

- Make pixel size threshold configurable for layers like **landuse** and **water**. ([#202](https://github.com/tilezen/vector-datasource/issues/202))

- For label placements, enable configurable pixel size threshold. ([#810](https://github.com/tilezen/vector-datasource/issues/810))

- Use json types and functions compatible with postgresql 9.3 to support better hstore tag usage. ([#826](https://github.com/tilezen/vector-datasource/issues/826))

- Migrate more pois layer transform functions to yaml (leisure, transit station states, aeroway gates). ([#754](https://github.com/tilezen/vector-datasource/issues/754).

- Add ability to set configurable buffer for MVT format per layer and geometry type. The default MVT config remains clipped (un-buffered), however. ([#106](https://github.com/tilezen/vector-datasource/issues/106))

- Remove **TileStache** dependency, moving Python transforms into **vector-datasource** repo. ([#211](https://github.com/tilezen/vector-datasource/issues/211))


v0.10.5
-------
* **Release date**: 2016-08-17
* Backport moving label generation to database. See [#965](https://github.com/tilezen/vector-datasource/issues/965).

v0.10.4
-------
* **Release date**: 2016-06-28
* Update tilejson layers. See [#874](https://github.com/tilezen/vector-datasource/issues/872).

v0.10.3
-------
* **Release date**: 2016-05-20.
* Limit addresses to points. See [#834](https://github.com/mapzen/vector-datasource/issues/834).

v0.10.2
-------
* **Release date**: 2016-05-10.
* Add test to verify building heights and properties use the `_` separator. See [#806](https://github.com/mapzen/vector-datasource/issues/806).
* **Requires:** [tileserver v0.6.1](https://github.com/mapzen/tileserver/releases/tag/v0.6.1) and [tilequeue v0.9.0](https://github.com/mapzen/tilequeue/releases/tag/v0.9.0) and [TileStache v0.10.1](https://github.com/mapzen/TileStache/releases/tag/v0.10.1)

v0.10.1
-------
* **Release date**: 2016-05-06.
* Update state boundaries from NE to include statistical boundaries. See [#797](https://github.com/mapzen/vector-datasource/issues/797).
* **Requires:** [tileserver v0.6.1](https://github.com/mapzen/tileserver/releases/tag/v0.6.1) and [tilequeue v0.9.0](https://github.com/mapzen/tilequeue/releases/tag/v0.9.0) and [TileStache v0.10.0](https://github.com/mapzen/TileStache/releases/tag/v0.10.0)

v0.10.0
-------
* **Release date**: 2016-05-04.
* **Paths get a significant makeover** in the `roads` layer:
  * Many `path`, `footway`, and `cycleway` features are visible earlier up to zoom 11, based on their designation as or inclusion in walking and cycling networks.
  * If a track, major road, or minor road is part of a walking or cycling network it is also visible earlier.
  * Some `footway` and `stair` features are visible later than before at zoom 15.
  * Add `footway` property to disentangle `sidewalk` and `crossing` features from other footways.
  * Add `walking_network` property with values in `iwn`, `nwn`, `rwn`, and `lwn` to indicate features's international to local significance.
  * Add other additional properties: `bicycle`, `foot`, `horse`, `tracktype`, `incline`, `trail_visibility` and `sac_scale`.
  * Most paths are now named on introduction, before they were only available at zoom 14+.
  * See [#593](https://github.com/mapzen/vector-datasource/issues/593), [#596](https://github.com/mapzen/vector-datasource/issues/596), and [#775](https://github.com/mapzen/vector-datasource/issues/775).
* **Add bicycle properties** to the `roads` layer:
  * Add `is_bicycle_related` property, set to `true` when road is a cycleway, part of a cycling network, or has bicyle lanes or other cycling related infrastrucure.
  * Add `bicycle_network` property with values in `icn`, `ncn`, `rcn`, and `lcn` to indicate features's international to local significance.
  * Add properties for `cycleway`, `cycleway_left`, `cycleway_right`, `oneway_bicycle`, and `segregated`.
  * See [#647](https://github.com/mapzen/vector-datasource/issues/647).
* **Add new outdoors related polygons** to the `landuse` layer:
  * `battlefield`, `beach_resort`, `boat_storage`, `caravan_site`, `dam`, `dog_park`, `firepit`, `fishing_area`, `fort`, `monument`, `picnic_site`, `recreation_track`, `rock`, `scree`, `stone`, `summer_camp`, `swimming_area`, and `water_park`.
  * See [#663](https://github.com/mapzen/vector-datasource/issues/663) and [#655](https://github.com/mapzen/vector-datasource/issues/655).
* **Add new natural lines** to the `landuse` layer:
  * `tree_row` and `hedge`.
  * See [#566](https://github.com/mapzen/vector-datasource/issues/566).
* **Add outdoor related points** to the `pois` layer:
  * `adit`, `battlefield`, `bbq`, `beach_resort`, `beacon`, `bicycle_repair_station`, `boat_rental`, `boat_storage`, `caravan_site`, `communications_tower`, `cross`, `dam`, `dive_centre`, `dog_park`, `dune`, `egress`, `firepit`, `fishing_area`, `fishing`, `fort`, `gas`, `geyser`, `hazard`, `hot_spring`, `hunting`, `life_ring`, `mast`, `mineshaft`, `monument`, `motorcycle`, `observatory`, `offshore_platform`, `outdoor`, `petroleum_well`, `picnic_site`, `picnic_table`, `power_pole`, `power_tower`, `put_in_egress`, `putin`, `pylon`, `ranger_station`, `rapid`, `recreation_track`, `rock`, `saddle`, `scuba_diving`, `shower`, `sinkhole`, `stone`, `summer_camp`, `swimming_area`, `telescope`, `trailhead`, `waterfall`, `waste_disposal`, `water_park`, `water_point`, `water_tower`, `water_well`, and `watering_place`.
  * See [#594](https://github.com/mapzen/vector-datasource/issues/594), [#599](https://github.com/mapzen/vector-datasource/issues/599), [#602](https://github.com/mapzen/vector-datasource/issues/602), [#657](https://github.com/mapzen/vector-datasource/issues/657), [#662](https://github.com/mapzen/vector-datasource/issues/662), [#663](https://github.com/mapzen/vector-datasource/issues/663), [#671](https://github.com/mapzen/vector-datasource/issues/671), [#674](https://github.com/mapzen/vector-datasource/issues/674), and [#675](https://github.com/mapzen/vector-datasource/issues/675).
* **Add outdoor related lines** to the `roads` layer.
  * `portage_way`
  * See [#677](https://github.com/mapzen/vector-datasource/issues/677).
* Add `dam` to the `boundaries` layer, and removed it from the `water` layer. See [#663](https://github.com/mapzen/vector-datasource/issues/663) and [#773](https://github.com/mapzen/vector-datasource/issues/773).
* Add `waterfall` features to the `pois` layer:
  * Includes `height` value in integer meters.
  * Zoom visibility is based on waterfall height: taller than 300 meters are visible at zoom 12 and waterfalls with height less than 50 meters are visible at zoom 14.
  * See
[#677](https://github.com/mapzen/vector-datasource/issues/677).
* Modified `peak` features in the `pois` layer:
  * Add new `elevation` value in integer meters.
  * Show some tall peaks at earlier zooms.
  * Add `tile_kind_rank` for peaks to throttle visibility of dense peak clusters.
  * See [#523](https://github.com/mapzen/vector-datasource/issues/523) and [#524](https://github.com/mapzen/vector-datasource/issues/524).
* Add `intermittent` property to `water` layer features:
  * Value of `yes` allows styling to distingish streams that do not run year round.
  * See
[#668](https://github.com/mapzen/vector-datasource/issues/668).
* Add **whitewater** related points to the `pois` layer:
  * `putin`, `egress`, `put_in_egress`, `hazard` and `rapid`.
  * Related: `portage_way` features added in the `roads` layer.
  * See [#599](https://github.com/mapzen/vector-datasource/issues/599).
* Add `bicycle_junction` features in `pois` layer:
  * A common European feature in signed bicycle routes with named junctions, these features are added at zoom 16.
  * The cycle network reference point's `ref` value is derived from one of `icn_ref`, `ncn_ref`, `rcn_ref` or `lcn_ref`, in descending order and is suitable for naming or use in a shield.
  * See [#592](https://github.com/mapzen/vector-datasource/issues/592).
* Add `cycle_barrier` features to the `pois` layer at zoom 18. See [#592](https://github.com/mapzen/vector-datasource/issues/592).
* Modify existing bicycle related features in `pois` layer:
  * `bicycle` shops are now visible earlier at zoom 15.
  * `bicycle_rental` is now visible at zoom 16.
  * `bicycle_rental_station` are split off from `bicycle_rental` shops and are visible at zoom 17. They include additional properties for `capacity` (an integer value), `network`, `operator`, and `ref`.
  * Features of kind `bicycle_parking` gain additional properties for `access`, `capacity`, `covered`, `fee`, `operator`, `maxstay`, and `surveillance`.
  * See [#592](https://github.com/mapzen/vector-datasource/issues/592).
* Add features of kind `walking_junction` to the `pois` layer:
  * Walking junctions are common in Europe for signed walking routes with named junctions, added at zoom 16.
  * The walking network reference point's `ref` value is derived from one of `iwn_ref`, `nwn_ref`, `rwn_ref` or `lwn_ref`, in descending order and is suitable for naming or use in a shield.
  * See [#592](https://github.com/mapzen/vector-datasource/issues/592).
* Add `island`, `islet`, and `archipelago` label placement points to the `earth` layer. See [#399](https://github.com/mapzen/vector-datasource/issues/399).
* Add `cliff` and `arete` lines to `earth` layer. See [#601](https://github.com/mapzen/vector-datasource/issues/601).
* Add label placement lines for `ridge` and `valley` to the `earth` layer. See [#601](https://github.com/mapzen/vector-datasource/issues/601).
* Move `continent` label placements to the `earth` layer from the `places` layer, a breaking change. See [#703](https://github.com/mapzen/vector-datasource/issues/703).
* Move `ocean` and `sea` label positions to the `water` layer from the `places` layer, a breaking change. See [#148](https://github.com/mapzen/vector-datasource/issues/148).
* Normalize `kind` values in the `boundaries` layer, a breaking change:
  * Match Natural Earth `kind` values to those coming from OpenStreetMap.
  * Remove junk statistical boundaries.
  * Remove Natural Earth's `type` property.
  * See [#517](https://github.com/mapzen/vector-datasource/issues/517) and [#687](https://github.com/mapzen/vector-datasource/issues/687).
* Normalize `kind` values in the `water` layer, a breaking change:
  * Match Natural Earth `kind` valeus to those coming from OpenStreetMap.
  * Example 1: use kind `ocean` instead of `Ocean`
  * Example 2: use kind `lake` with `reservoir:yes` instead of `Reservoir`.
  * Example 3: use kind `ocean` with `boundary:yes` instead of `Coastline`.
  * See [#628](https://github.com/mapzen/vector-datasource/issues/628) and
[#680](https://github.com/mapzen/vector-datasource/issues/680)
* Add `sources` to the `earth` layer:
  * Indicate `naturalearth.com`, `openstreetmapdata.com`, or `openstreetmap.org` as source.
  * See [#737](https://github.com/mapzen/vector-datasource/pull/737)
* Bug fixes:
  * Identify `yes` kind `pois` to their respective values, including generic `office`. See [#705](https://github.com/mapzen/vector-datasource/issues/705).
  * Don't merging lines in the `roads` layer at zoom 16 (the max zoom). See [#766](https://github.com/mapzen/vector-datasource/issues/766).
  * Line merging in the `roads` layer should produce long lines, not many 2 segment lines. See [#768](https://github.com/mapzen/vector-datasource/issues/768).
  * Removed reference to non-existant `highway=minor` and `highway=footpath` in `roads` layer queries. See [#680](https://github.com/mapzen/vector-datasource/issues/680).
* Refactor how we calculate `kind` values using YAML config files across all layers to provide more determinism and eliminate `yes` values. Follow on to v0.9 changes in [#580](https://github.com/mapzen/vector-datasource/issues/580) and [#282](https://github.com/mapzen/vector-datasource/issues/282). See [#646](https://github.com/mapzen/vector-datasource/issues/646) and [#687](https://github.com/mapzen/vector-datasource/issues/687)
* Update how we handle OpenStreetMap data updates via planet_osm_rels triggers. See [#711](https://github.com/mapzen/vector-datasource/issues/711).
* **Requires:** [tileserver v0.6.1](https://github.com/mapzen/tileserver/releases/tag/v0.6.1) and [tilequeue v0.9.0](https://github.com/mapzen/tilequeue/releases/tag/v0.9.0) and [TileStache v0.10.0](https://github.com/mapzen/TileStache/releases/tag/v0.10.0)


v0.9.1
------
* **Release date**: 2016-03-28. _Live in prod: 2015-03-30._
* Ensure all `transit` layer features are included at zoom 16+. See [commit](https://github.com/mapzen/vector-datasource/commit/9a279d9c29dc63e4e7270a3d846e96a7843bb86b).
* **Requires:** [tileserver v0.6.1](https://github.com/mapzen/tileserver/releases/tag/v0.6.1) and [tilequeue v0.8.0](https://github.com/mapzen/tilequeue/releases/tag/v0.8.0) and [TileStache v0.9.0](https://github.com/mapzen/TileStache/releases/tag/v0.9.0)

v0.9.0
------
* **Release date**: 2016-03-24. _Live in prod: 2015-03-30._
* Adjust tile rank for `station` features in the `pois` layer, emphasizing rail stations over other types of transit. See [#506](https://github.com/mapzen/vector-datasource/issues/506).
* Remove long tail of less important `station` features from mid-zooms in the `pois` layer. See [#506](https://github.com/mapzen/vector-datasource/issues/506).
* Show more `station` features in the `pois` layer by limiting "merging" to zooms less than 15. See [#506](https://github.com/mapzen/vector-datasource/issues/506).
* Show existing aerialway `station` & railway `tram_stop` features in the `pois` layer earlier at zoom 13. See [#587](https://github.com/mapzen/vector-datasource/issues/587).
* Add several boolean values to indicate `station` transit service types in `pois` layer. See [#352](https://github.com/mapzen/vector-datasource/issues/352).
* Add `state` property to `station` features in the `pois` layer to indicate planned and under construction features. See [#484](https://github.com/mapzen/vector-datasource/issues/484).
* Add optional `root_relation_id` ID value on transit `station` features in the `pois` layer. See [#590](https://github.com/mapzen/vector-datasource/issues/590). **CORRECTED 9/31:** earlier documentation said `osm_site_relation`.
* Add optional `uic_ref` to `station` features in the `pois` layer.
* Add additional transit points to `pois` layer and lines to the `transit` layer for grab bag of stops, halts, stop areas, and platforms. See [#469](https://github.com/mapzen/vector-datasource/issues/469).
* Show `transit` layer features at earlier zoom levels, including international `train`, `subway`, `light_rail`, and `tram`. See [#472](https://github.com/mapzen/vector-datasource/issues/472).
* Add `funicular` and `monorail` features to the `transit` layer. See [#588](https://github.com/mapzen/vector-datasource/issues/588).
* Remove physical `railway` from the `transit` layer; they don't have passenger service. See [#501](https://github.com/mapzen/vector-datasource/issues/501).
* Add `service` values to `transit` layer line features to indicate international, national, and regional importance. See [#471](https://github.com/mapzen/vector-datasource/issues/471).
* Add a new boolean `is_bus_route` property to features in the `roads` layer starting at zoom 12 if any `bus` or `trolley_bus` route passes along the way. No indication is provided for which bus routes at this time. See [#611](https://github.com/mapzen/vector-datasource/issues/611).
* Add `subway` and `funicular` lines to `roads` layer as a type of `rail`. See [#549](https://github.com/mapzen/vector-datasource/issues/549) and [#510](https://github.com/mapzen/vector-datasource/issues/510).
* Remove `disused` features from the `pois` layer, for instance disused railway stations. See [#368](https://github.com/mapzen/vector-datasource/issues/368).
* Limit visibility of `closed` and `historical` features to zoom 17+ in the `pois` and `buildings` layers. See [#291](https://github.com/mapzen/vector-datasource/issues/291) and [#483](https://github.com/mapzen/vector-datasource/issues/483).
* Remove internal `mz_is_building` property from features in the `landuse` layer. See [#333](https://github.com/mapzen/vector-datasource/issues/333).
* Document recommended **overlay** and **underlay** sort_key orders. See [#586](https://github.com/mapzen/vector-datasource/issues/586).
* Move much of the `kind` calculation logic from pure SQL to CSV spreadsheets for easier config and address outstanding SQL coalesce bugs. See [#580](https://github.com/mapzen/vector-datasource/issues/580) and [#282](https://github.com/mapzen/vector-datasource/issues/282).
* Normalize `source` property across all layers. If you have custom place filters, this will be a breaking change. See [#503](https://github.com/mapzen/vector-datasource/issues/503).
* **Requires:** [tileserver v0.6.1](https://github.com/mapzen/tileserver/releases/tag/v0.6.1) and [tilequeue v0.8.0](https://github.com/mapzen/tilequeue/releases/tag/v0.8.0) and [TileStache v0.9.0](https://github.com/mapzen/TileStache/releases/tag/v0.9.0)


v0.8.0
------
* **Release date**: 2016-03-04. _Live in prod: 2015-03-08._
* Add new label placements in the `water` layer for `bay`, `strait`, and `fjord`. [Issue #400](https://github.com/mapzen/vector-datasource/issues/400)
* Add new kinds in the `pois` layer for `hardware` and `trade` to capture more types of "big box" stores. [Issue #520](https://github.com/mapzen/vector-datasource/issues/520)
* Additions to the `pois` layer to celebrate [International Women's Day](http://www.internationalwomensday.com). [Issue #526](https://github.com/mapzen/vector-datasource/issues/526)
     * Basic mappings: `childcare`, `clinic`, `dentist`, `doctors`, `kindergarten`, `midwife`, `phone`, `social_facility`, and `toilets`.
     * Most social facility are indicated by their detailed kind. Common kinds: `ambulatory_care`, `assisted_living`, `food_bank`, `group_home`, `outreach`, `shelter`, `workshop`, see [TagInfo](https://taginfo.openstreetmap.org/keys/social_facility#values) for full set.
* Large hotels and "big box" stores now appear at earlier zooms in the `pois` layer. Issues [520](https://github.com/mapzen/vector-datasource/issues/520) and [522](https://github.com/mapzen/vector-datasource/issues/522)
* The `pois` layer now inludels all features at zoom 16 that were only available in zoom 17 and 18 previously. But we now include a recommended `min_zoom` to replicate the earlier behavior. [Issue #478](https://github.com/mapzen/vector-datasource/issues/478)
* Improved station `tile_kind_rank` values in the `pois` layer by including more data. Railway route extraction no longer relies on the `planet_osm_nodes` table, which may be missing if flat nodes is enabled. [Issue #507](https://github.com/mapzen/vector-datasource/issues/507)
* The `buildings` layer now includes all buildings (no filter) at zoom 16, with `min_zoom` properties being added at zoom >= 16. Addresses are included at zoom 16 but are marked `min_zoom:17`. [Issue #557](https://github.com/mapzen/vector-datasource/issues/557)
* In the `boundaries` layer `fences` are now included at zoom 16 (was 17). [Issue #478](https://github.com/mapzen/vector-datasource/issues/478)
* The `roads` and `landuse` layers receive a significant overhall to `sort_key` values. The `sort_key` value is a suggestion for which order to draw features. The value is an integer where smaller numbers suggest that features should be "behind" features with larger numbers. Issues [364](https://github.com/mapzen/vector-datasource/issues/364) and [546](https://github.com/mapzen/vector-datasource/issues/546)
* More layers include `sort_key` values including `boundaries`, `buildings`, `earth`, `transit`, and `water` that are compatible with the values in the `roads` and `landuse` layers. [Issue #550](https://github.com/mapzen/vector-datasource/pull/550)
* Fixed migration loop to handle the case where there are no explicit migrations to run. [Issue #514](https://github.com/mapzen/vector-datasource/issues/514)
* **Requires:** [tileserver v0.6.0](https://github.com/mapzen/tileserver/releases/tag/v0.6.0) and [tilequeue v0.8.0](https://github.com/mapzen/tilequeue/releases/tag/v0.8.0) and [TileStache v0.8.0](https://github.com/mapzen/TileStache/releases/tag/v0.8.0)

v0.7.0
------

* **Release date**: 2016-01-19. _Live in prod: 2015-01-25._
* At mid and low zooms, roads have some properties dropped and are then merged together. This produces a huge reduction in the number of features in a tile and helps reduce both tile size and rendering time. [Issue](https://github.com/mapzen/vector-datasource/issues/358), [Issue](https://github.com/mapzen/vector-datasource/issues/489).
* Gym / fitness POIs are now available with `kind: fitness` in the `pois` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/465).
* Swimming pools are now available with `kind: swimming_pool` in the `water` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/443).
* Prisons are now available with `kind: prison` in both the `pois` and `landuse` layers. [Issue](https://github.com/mapzen/vector-datasource/issues/370).
* Electronics shops are now available with `kind: electronics` in the `pois` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/374).
* Aeroway gates are now available with `kind: gate` and `aeroway: gate` in the `pois` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/454).
* Motorway links no longer show at zooms 10 and below. [Issue](https://github.com/mapzen/vector-datasource/issues/488).
* Buildings are now clipped to a 3x expanded tile boundary. This limits the maximum extent of buildings and can help if you've been experiencing rendering artefacts with very large buildings. [Issue](https://github.com/mapzen/vector-datasource/issues/490), [Issue](https://github.com/mapzen/vector-datasource/issues/197).
* Zoos and other tourist attractions have been "fixed up", and now contain a much wider range of features, as well as including more attributes such as surface type. [Issue](https://github.com/mapzen/vector-datasource/issues/440).
* **Requires:** [tileserver v0.5.0](https://github.com/mapzen/tileserver/releases/tag/v0.5.0) and [tilequeue v0.7.0](https://github.com/mapzen/tilequeue/releases/tag/v0.7.0) and [TileStache v0.7.0](https://github.com/mapzen/TileStache/releases/tag/v0.7.0)

v0.6.0
------
* **Release date**: 2015-12-16. _Live in prod: 2015-01-08._
* Highway exits are now present in the `pois` layer, with `kind:motorway_junction` and, if the data is available, properties for `exit_to` directions and `ref` reference number. [Issue](https://github.com/mapzen/vector-datasource/issues/160).
* Beach polygons are now present in the `landuse` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/366).
* Military (and rural) `landuse` areas were not being output due to a bug. This has been fixed and both landuse types are now being output. [Issue](https://github.com/mapzen/vector-datasource/issues/367).
* Railway platforms are now present in the `transit` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/244).
* Features related to winter sports are now present; with pistes in the `roads` layer as `kind:piste`, winter sports areas / resorts in the `landuse` layer with `kind:winter_sports` and various `pois` related to ski/snowboard hire available in the `pois` layer. [Pistes ticket](https://github.com/mapzen/vector-datasource/issues/342). [Areas ticket](https://github.com/mapzen/vector-datasource/issues/343), [POIs ticket](https://github.com/mapzen/vector-datasource/issues/344).
* IATA codes are included as the `iata` property on airports for which the data is available in the `pois` and `landuse` layers. [Issue](https://github.com/mapzen/vector-datasource/issues/398).
* Pier lines are now included in the `roads` layer with `kind:path, man_made:pier`. [Issue](https://github.com/mapzen/vector-datasource/issues/382).
* Subway stations show at zoom 12 in the `pois` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/369).
* Zoos now show up by zoom 13 at the latest in the `pois` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/421).
* Ice cream shops and stands are now included in the `pois` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/447)
* Toy shops are now included in the `pois` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/404).
* Wine shops are now included in the `pois` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/448)
* Alcohol shops are now included in the `pois` layer. [Issue](https://github.com/mapzen/vector-datasource/issues/448)
* The `population` attribute in the `places` layer is now always an integer. [Issue](https://github.com/mapzen/vector-datasource/issues/230).
* **Requires:** [tileserver v0.5.0](https://github.com/mapzen/tileserver/releases/tag/v0.5.0) and [tilequeue v0.6.0](https://github.com/mapzen/tilequeue/releases/tag/v0.6.0) and [TileStache v0.6.0](https://github.com/mapzen/TileStache/releases/tag/v0.6.0)

v0.5.3
------
* **Release date**: 2015-12-07. _Live in prod: 2015-12-07._
* Fix bug where school points were not being exported as POIs. [Issue](https://github.com/mapzen/vector-datasource/issues/417).
* **Requires:** [tileserver v0.4.1](https://github.com/mapzen/tileserver/releases/tag/v0.4.2) and [tilequeue v0.5.1](https://github.com/mapzen/tilequeue/releases/tag/v0.5.1) and [TileStache v0.5.1](https://github.com/mapzen/TileStache/releases/tag/v0.5.1)

v0.5.2
------
* **Release date**: 2015-12-04. _Live in prod: 2015-12-04._
* Make hospital POIs visible at zoom 14 by default, instead of 15. [Issue](https://github.com/mapzen/vector-datasource/issues/420).
* Fix regression which dropped parking aisles. [Issue](https://github.com/mapzen/vector-datasource/issues/412).
* **Requires:** [tileserver v0.4.1](https://github.com/mapzen/tileserver/releases/tag/v0.4.2) and [tilequeue v0.5.1](https://github.com/mapzen/tilequeue/releases/tag/v0.5.1) and [TileStache v0.5.1](https://github.com/mapzen/TileStache/releases/tag/v0.5.1)

v0.5.1
------
* **Release date**: 2015-11-24. _Live in prod: 2015-11-24._
* Update landuse query to use existing index
* **Requires:** [tileserver v0.4.1](https://github.com/mapzen/tileserver/releases/tag/v0.4.2) and [tilequeue v0.5.1](https://github.com/mapzen/tilequeue/releases/tag/v0.5.1) and [TileStache v0.5.1](https://github.com/mapzen/TileStache/releases/tag/v0.5.1)

v0.5.0
------
* **Release date**: 2015-11-13. _Live in prod: 2015-11-20._
* Filter out duplicate POIs in `pois`, `landuse`, and `buildings` layers, preferring poi layer features. Includes density filter.
* Add neighbourhoods (and macrohoods and microhoods) from Who's On First in the `places` layer. New properties: `min_zoom`, `max_zoom`, `kind_tile_rank`, `is_landuse_aoi`.
* Remove neighbourhoods from OpenStreetMap.
* Add `kind_tile_rank` to `kind=station` features to enable filtering out of less important transit stations at low zooms (to reduce crowding). Weights stations that are shown at lower zoom levels by lines going through them. Lower numbers = more important.
* Stop duplicating building footprints into the landuse layer, and exclude building=no features. Include all building properties at all zooms (was limited to high zooms).
* Use addr:housename as building name if feature is a POI
* Add aerialway line features into the `roads` layer.
* Add back missing roads on park and other landuse boundaries that went missing when `landuse_kind` intercut was added.
* Add service levels to railroads features in `roads` layer to distinguish importance.
* Updated High Road classifier (zoom range, sort order) for `service` roads, including pedestrian streets, paths, and forest tracks so they are visible earlier.
* Add `volume` on `building` layer polygons to enable more sophisticated client-side filtering at mid zooms.
* Add `city_wall` lines and `barrier` lines to `boundaries` layer.
* Fix minor bug around missing `water` layer boundary lines.
* Add `area` to water boundary lines (so filtering of boundary lines can match polygons).
* Add `townhall`, `laundry`, `dry_cleaner`, and `ferry_terminal` to `pois` layer.
* Move centroid calculation out of database to post-processing step
* Updated formats to contain `api_key` parameter in tilejson metadata URL
* **Requires:** [tileserver v0.4.1](https://github.com/mapzen/tileserver/releases/tag/v0.4.1) and [tilequeue v0.5.0](https://github.com/mapzen/tilequeue/releases/tag/v0.5.0) and [TileStache v0.5.0](https://github.com/mapzen/TileStache/releases/tag/v0.5.0)

v0.4.2
------
* **Release date:** 2015-10-14. _Live in prod: 2015-10-20._
* Fix invalid Antarctica polygon in buffered land.
* **Requires:** [tileserver v0.4.0](https://github.com/mapzen/tileserver/releases/tag/v0.4.0) and [tilequeue v0.4.1](https://github.com/mapzen/tilequeue/releases/tag/v0.4.1) and [TileStache v0.4.1](https://github.com/mapzen/TileStache/releases/tag/v0.4.1)

v0.4.1
------
* **Release date:** 2015-10-13. _Live in prod: 2015-10-20._
* Create new indexes to speed up query times
* Reduce `boundaries` query payload size
* **Requires:** [tileserver v0.4.0](https://github.com/mapzen/tileserver/releases/tag/v0.4.0) and [tilequeue v0.4.1](https://github.com/mapzen/tilequeue/releases/tag/v0.4.1) and [TileStache v0.4.1](https://github.com/mapzen/TileStache/releases/tag/v0.4.1)

v0.4.0
------
* **Release date:** 2015-10-06. _Live in prod: 2015-10-20._
* Fix regression in v0.3.0 where zooms 0 to zoom 8 country and region (state, province) features from OpenStreetMap were dropped from tiles (rolling back a change in v0.2.0)
* Greater diversity of label placements for POIs, landuse, and buildings result in more balanced selection of features visible at mid and high (neighborhood) zooms. The feature's minimum recommended visible zoom is now included as a property (eg: `min_zoom=10.7763`), useful for determining feature priority in client-side label collisions. Currently visibility should be calculated combined with area filters, we'll move that serverside in later releases.
* Add label positions for water bodies to the `water` layer noted as `label_position=yes`.
* Add label positions for buildings to the `buildings` layer noted as `label_position=yes`.
* Landuse label positions are now additionally available in the `landuse` layer directly, noted with `label_position=yes`.
* **WARNING:** The existing `landuse-labels` layer will be depreciated in a later release.
* Add `location` and `layer` tags to buildings features in the `buildings` layer to determine if something is `location=underground` or `layer=-1` (like BART stations in San Francisco).
* Administrative boundary line improvements are back in the `boundaries` layer: now based on OSM relations, includes localized left- and right-names, and adds `maritime_boundary=yes` when the boundary is out in the deep sea. Note that this is slightly different than the `maritime=yes` tag that comes directly from OSM as we're calculating it using a custom spatial mask that will be improved over time.
* Add `ferry` lines starting at zoom 8 to `road` layer.
* Add airport `runway` lines starting at zoom 9 in the `roads` layer. Can be combined with `landuse_kind` attributes to throttle visibility.
* **Requires:** [tileserver v0.4.0](https://github.com/mapzen/tileserver/releases/tag/v0.4.0) and [tilequeue v0.4.0](https://github.com/mapzen/tilequeue/releases/tag/v0.4.0) and [TileStache v0.4.0](https://github.com/mapzen/TileStache/releases/tag/v0.4.0)

v0.3.0
------
* **Release date:** 2015-09-25
* Source `national_park`, `protected_area` and other significant landuse boundaries from OpenStreetMap to generate AOI polygons and labels earlier starting at zoom 4 globally (was zoom 9). These features also gain  `protect_class` and `operator` properties.
* Add OSM roads and other features starting at zoom 8 (transition from Natural Earth data was zoom 9 in earlier releases). Natural Earth urban areas remain until zoom 9, though.
* Add water boundaries for low zooms (from Natural Earth), to match earlier `v0.2.0` work for OSM water boundaries at mid and high zooms.
* Landuse AOI polygons now include a `sort_key` hint from the server for easier client side styling. The `sort_key` is used server side to make the `landuse_kind` predictable on roads.
* Underground streams are now marked such with a additional `is_tunnel` property (zooms 11+)
* Temporarily reverted changes to administrative boundary lines in `v0.2.x` that dropped some boundary lines and their `kind` attributes. They'll be back soon, better than ever.
* Other minor bug fixes and optimizations.
* **Requires:** [tileserver v0.3.0](https://github.com/mapzen/tileserver/releases/tag/v0.3.0) and [tilequeue v0.3.0](https://github.com/mapzen/tilequeue/releases/tag/v0.3.0) and [TileStache v0.3.0](https://github.com/mapzen/TileStache/releases/tag/v0.3.0)

v0.2.0
-----
* **Release date:** 2015-09-18
* Add `landuse_kind` to features in `roads` and `buildings` layers based on the intersection with `landuse` layer features. **TIP:** custom style roads and buildings over parks and other area features to improves contrast.
* Add calculated water `boundary=yes` line features to `water` layer to resolve funky "coastlines" crossing water polygons (where river and ocean polygons meet, and where adjacent river polygons meet). There are already stream lines in the water layer, but this might require an style update. **TIP:** In D3.js, set `fill: none` on linear features like streams and `boundary=yes` feeatures.
* Added power station polygons to `landuse` layer with `kind` = `plant`, `generator`, or `substation`.
* Add house addresses points to `buildings` layer with `kind` = `address`.
* Resolve duplicate populated places from `places` layer. Natural Earth only used in low zooms, OSM only used in mid and high zooms.
* Stop generating tiny invalid geoms that were making D3.js cry.
* **Requires:** [tileserver v0.2.0](https://github.com/mapzen/tileserver/releases/tag/v0.2.0) and [tilequeue v0.2.0](https://github.com/mapzen/tilequeue/releases/tag/v0.2.0) and [TileStache v0.2.0](https://github.com/mapzen/TileStache/releases/tag/v0.2.0)

v0.2.0-prehistory
------
* **Release date:** July-August 2015
* Add missing OSM `city` features to `places` layer in mid and high zooms.
* Add `kind` = `aerodrome` (airport AOI), `military`, `zoo`; man made features of `kind` = `pier`, `wastewater_plant`, `works`, `bridge`, `tower`, `breakwater`, `water_works`, `groyne`, `dike`, `cutline`; and `urban` & `rural` polygons to `landuse` and points to `landuse-labels` layers.
* Add `sport` and `religion` tags to `landuse` layer polygon and `landuse-labels` point features to distinguish different kinds of sport pitches and places of worship. **TIP:** use these to stylize custom icons.
* Add `cuisine`, `sport` and `religion` tags to `pois` layer point features to distinguish different kinds of restaurants, sport pitches, and places of worship.  **TIP:** use these to stylize custom icons.
* Add more POIs with **`craft`** set to `kind` = `brewery`, `carpenter`, `confectionery`, `dressmaker`, `electrician`, `gardener`, `handicraft`, `hvac`, `metal_construction`, `painter`, `photographer`, `photographic_laboratory`, `plumber`, `pottery`, `sawmill`, `shoemaker`, `stonemason`, `tailor`, `winery` and with **`office`** set to `kind` = `accountant`, `administrative`, `advertising_agency`, `architect`, `association`, `company`, `consulting`, `educational_institution`, `employment_agency`, `estate_agent`, `financial`, `foundation`, `government`, `insurance`, `it`, `lawyer`, `newspaper`, `ngo`, `notary`, `physician`, `political_party`, `religion`, `research`, `tax_advisor`, `telecommunication`, `therapist`, `travel_agent`, `yes`) so more business icons are included in tiles.
* Stop including `parking` and `bus_stop` point features in `pois` layer until zoom 17.
* Stop including `parking` polygon features in `landuse-labels` layer until zoom 17.
* Less linework geometry simplification on Natural Earth geometries at low zooms.
* Move to query templates to reduce code complexity.
* Start [managing issues](https://waffle.io/mapzen/vector-datasource) across all Mapzen vector tile repos with Waffle.io.

v0.1.0
------
* **Release date:** 2015-05-12
* See also: [inaugural Mapzen Vector Tiles blog post](https://mapzen.com/blog/look-upon-our-squares-of-math-in-three-dimensions)

NOTE: Release dates reflect date repo was tagged or otherwise released. Date that production tiles reflect same changes may lag (around a week, usually less).
