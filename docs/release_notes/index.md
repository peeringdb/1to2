# Release Notes

The release notes list the GitHub issues and a summary of what has changed in PeeringDB software releases.

Each new release has a one week beta test period on the [beta server](https://beta.peeringdb.com/) before it goes live.  The beta and new releases are announced on the [PeeringDB Announce Mailing List](https://lists.peeringdb.com/cgi-bin/mailman/listinfo/pdb-announce) and on [Twitter](https://twitter.com/PeeringDB), [LinkedIn](https://www.linkedin.com/company/peeringdb) and [Facebook](https://www.facebook.com/peeringdb).

## Release 2.28.0

Beta Announcement Date: 14 July 2021
Release Date: 21 July 2021

| **GitHub Issue** | **Summary** |
| ----------------- | ----------- |
| [#23 make websearch smarter ](https://github.com/peeringdb/peeringdb/issues/23) | Provide a better search experience for quick search, advanced search and API filtering. The key features are properly indexed search, which supports search based on partial name matches, and geocoded search, which supports search based on coordinates. |
| [#965 IX-F importer: intermittent bug during consolidation of notifications ](https://github.com/peeringdb/peeringdb/issues/965) | Fixes a bug with the IX-F Member Export importer that resulted in intermittent import failures. |
| [#863 Improve error handling when a user tries to add an object which is already there ](https://github.com/peeringdb/peeringdb/issues/863) | Increases visibility of field validation error notes by increasing size and font weight. |
| [#375 On changing email address rescan open affiliation requests ](https://github.com/peeringdb/peeringdb/issues/375) | When a user changes their e-mail address we now automatically re-evaluate any open affiliation request that the user has that are tied to an ASN. |
| [#923 Prevent deletion of a last technical contact if there is an existing netixlan object ](https://github.com/peeringdb/peeringdb/issues/923) | Prevents deletion of the last technical contact of existing `netixlan`, i.e. enforce that `netixlan` should always have at least one technical contact |

## Release 2.27.1

Beta Announcement Date: 19 May, 2021
Release Date: 26 May, 2021

| **GitHub Issue** | **Summary** |
| ----------------- | ----------- |
| [#946 Evaluate non-google map/geo sources ](https://github.com/peeringdb/peeringdb/issues/946) | Evaluated alternative geo data APIs and selected Melissa. |
| [#802 Extend Advanced Search for IXes and Facilities ](https://github.com/peeringdb/peeringdb/issues/802) | Adds search filters to advanced search (ix capacity search, organization presence search, and network presence search.) |
| [#799 Additional self-selection fields for IX objects ](https://github.com/peeringdb/peeringdb/issues/799) | Added `service_level` and `terms` fields to InternetExchange objects to allow exchanges to share additional ifnormation about their offering. These are supported as filters in the advanced search. |
| [#834 Add ix_count to object fac ](https://github.com/peeringdb/peeringdb/issues/834) | In the API, added a read-only field to `fac` called `ix_count` that counts the number of exchanges the linked to the facility). |
| [#835 Add {ix,fac}_count to object net ](https://github.com/peeringdb/peeringdb/issues/835) | In the API, added read-only fields to `net` called `ix_count` and `fac_count` that count the number of exchanges and facilities linked to the network). |
| [#836 Add fac_count to object ix ](https://github.com/peeringdb/peeringdb/issues/836) | In the API, added a read-only field to `ix` called `fac_count` that counts the number of facilities in which the exchange has a presence. |
| [#922 Circumvent approval of a facility by deleting and re-adding ](https://github.com/peeringdb/peeringdb/issues/922) | Fixed bug where if a user deletes a status "pending" fac, they can re-add it and it will be status "ok" (should be "pending"). |
| [#810 Get rid of the 'Protocols supported' fields / UI for IXes ](https://github.com/peeringdb/peeringdb/issues/810) | Removed `proto_unicast`, `proto_multicast`, and `proto_ipv6` fields from `ix` UI. The fields remain in the v2 api but `proto_ipv6` and `proto_unicast` will be populated from the existance of protocols in the exchange's `ixpfx` records. |
| [#985 500 Error on advanced search ](https://github.com/peeringdb/peeringdb/issues/885) | Resolved an issue where unauthenticated users got a 500 error in advanced search. |


## Release 2.26.1

Beta Announcement Date: 14 April, 2021
Release Date: 21 April, 2021

| **GitHub Issue** | **Summary** |
| ----------------- | ----------- |
| [#883 IXF-Importer: minimise emails to Support/DeskPRO/AC ](https://github.com/peeringdb/peeringdb/issues/883) | This change collates all importer suggestions into a single e-mail notification. |
| [#931 Limit the number of requests for affiliation to an ASN/org to 1 ](https://github.com/peeringdb/peeringdb/issues/931) | Limits the number of affiliation request to an ASN to just one. Provides visual feedback on subsequent request attempts. |
| [#913 API should do an IP6 address instead of a string match ](https://github.com/peeringdb/peeringdb/issues/913) | Normalizes how IPv6 addresses are stored in the database and updates existing IPv6 addresses in the databases and elsewhere. |


## Release 2.26.0

Beta Announcement Date: 10 March, 2021
Release Date: 24 March, 2021

| **GitHub Issue** | **Summary** |
| ----------------- | ----------- |
| [#266 Add API Keys ](https://github.com/peeringdb/peeringdb/issues/266) | This release introduces organization level [API Keys](https://github.com/peeringdb/peeringdb/blob/master/docs/api_keys.md). |
| [#827 Make GUI and API feature equivalent ](https://github.com/peeringdb/peeringdb/issues/827) | PeeringDB has a GUI and an API. This issue is a reminder to keep both feature equivalent. |
| [#865 Allow arbitrary decimal places as input for longitude and latitude. Systems rounds to six ](https://github.com/peeringdb/peeringdb/issues/865) | Allow arbitrary length of inputs to latitude and longitude. Round to 6 digits (including Google Maps output). |
| [#902 Add "long name" or "aka" field to 'fac' records ](https://github.com/peeringdb/peeringdb/issues/266) | add fields `aka` and `name_long` to object `fac`, `ix`, `net`, and `org`. |
| [#937 Geocode for org is broken ](https://github.com/peeringdb/peeringdb/issues/937) | This was fixed through work on #940. |
| [#939 Replace Validation Error with Validation "Warning" for geolocation validation ](https://github.com/peeringdb/peeringdb/issues/939) | If our address validation service cannot find an address corresponding to the user-inputed address it will allow the object to be saved and raise a "validation warning" in the meta object of the API response. The web UI will display a pop-up based on this warning. |
| [#940 Return geo-normalized fields as "suggested address" ](https://github.com/peeringdb/peeringdb/issues/940) | In an effort to normalize addresses, the system may overwrite the user input. In case of a mismatch, the user now is prompted with a "suggested address" and either confirms or rejects. In case of rejection, the address is taken as provided by the user. Please keep an eye on what you provided and what is suggested. The suggestion may flip street name and house name as well as cut off postal codes. |
| [#918 drop travis ci and move to github actions ](https://github.com/peeringdb/peeringdb/issues/918) | Changed CI environment to improve deployment speed. |

## Release 2.25.0

Release Date: 3 February, 2021

| **GitHub Issue** | **Summary** |
| ----------------- | ----------- |
| [#246 IXF should be IX-F ](https://github.com/peeringdb/peeringdb/issues/246) | This release introduces various spelling corrections. |
| [#828 IX-F importer: Handle ipv4/ipv6 on same vlan but separate connections ](https://github.com/peeringdb/peeringdb/issues/828) | This issue deals with how the IX-F importer handles information from the IX-F JSON import. PeeringDB handles both the IPv4 as well as the IPv6 address in the same object (`netixlan`). And from a peering partner pov this is ok as it doesn't matter whether these addresses are on the same interface or even same router. However, IX-F JSON differentiates. For the time being, the importer combines IPv4 and IPv6 if both are set to an operational status in the IX-F JSON. |
| [#846 IX-F importer: if ixf_ixp_member_list_url is null then ixf_ixp_import_enabled can't be true ](https://github.com/peeringdb/peeringdb/issues/846) | Apply logic to the meaning of `ixf_ixp_member_list_url`. i.e. only allow `ixf_ixp_import_enabled` to be set to `true` if a URL is specified. |
| [#875 "IXF-Importer: improved handling of how contacts are joined into direct conflict resolution deskpro tickets"](https://github.com/peeringdb/peeringdb/issues/875) | Resolved an issue where responses to automatically generated Deskpro tickets were routed to the wrong ticket. |
| [#878 IXF-Importer: reorder of email content ](https://github.com/peeringdb/peeringdb/issues/878) | This is mainly an internal improvement. And fixes also not disclosing private IXP information to the public. |
| [#882 IXF-Importer: don't abort when there is nothing to import ](https://github.com/peeringdb/peeringdb/issues/882) | If there is nothing to import from an IX-F JSON don't abort with an error message. |
| [#893 IX-F Importer: history of changes per ixlan & netixlan ](https://github.com/peeringdb/peeringdb/issues/893) | Fixed bug related to the logging of importer changes. |
| [#896 IX-F Importer: Bogus output of "Preview" tool ](https://github.com/peeringdb/peeringdb/issues/896) | Fixed a bug in the preview tool, where `invalid member type ignored` messages weren't filtered for the network viewing the preview. |
| [#888 Type issue when overriding settings through environment variables for numeric types ](https://github.com/peeringdb/peeringdb/issues/888) | Fixed a bug and now ensure that overrides are coerced to the correct expected type. |
| [#872 Update dependencies ](https://github.com/peeringdb/peeringdb/issues/872) | Updated container to python 3.9 and addressed all dependencies.|
| [#694 add syntactic sugar for entering port speeds ](https://github.com/peeringdb/peeringdb/issues/694) | Simplifies the UI for editing port speeds to make it more human friendly. |
| [#717 Loading time issue /cp facility view ](https://github.com/peeringdb/peeringdb/issues/717) | Fixed slow load or timeouts for loading data for some facilities |
| [#837 Provide a friendlier explanation when entering / changing a phone number ](https://github.com/peeringdb/peeringdb/issues/837) | Provides a tooltip to help people enter E.164 formatted telephone numbers. |
| [#541 When looking at a network record, show last updated ix<->net or fac<->net date ](https://github.com/peeringdb/peeringdb/issues/541) | Improved information about when records were last updated. |

## Older releases

* [2020 Release Notes](/release_notes/release_notes_2020/)
