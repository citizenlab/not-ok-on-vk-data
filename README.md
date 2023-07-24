# Data Release for "Not OK on VK: An Analysis of In-Platform Censorship on Russias VKontakte"

This repository is the associated raw data collected for the Citizen Lab report titled ["Not OK on VK: An Analysis of In-Platform Censorship on Russias VKontakte".](https://citizenlab.ca/2023/07/an-analysis-of-in-platform-censorship-on-russias-vkontakte)

The data is available in plaintext comma seperated value format (CSV).  Some files are compressed as ZIP format due to their size.


## Data Structure 

The data in this repository is collected from two network vantage points: Russia and Canada. The vantage point is denoted in the beginning of the CSV filename. For example RU_ is collected from a Russian network vantage point and CA_ is collected from a Canadian one.

VKontakte has three data divisions when performing a search: videos, communities (or clubs), people (or personal accounts).  The filename denotes which data is relevant in the file.  For example the filename RU_videos would be results that are missing in the search results for Russian videos.

There are three types of data collections also denoted in the filename.  These are:

* **initial** - This is the data as originally collected, and includes results that returned block messages as well as those that did not, which could be false positives.

* **inscope** - This is the data that has missing content but  only shows results that return error messages that are considered in scope for the research.  For example videos with messages asking users to sign in to view them are not considered in scope while those with legal justifications for inaccessible content are.

* **noduplicates** - No duplicates is the same as the in-scope scope collection but only shows unique URLs.  Different queries can lead to discovery of the same missing URL this collection only includes a single URL once.

For the report, some analysis was done using the **inscope** collection and some used the **noduplicates** version. For example to look at overall queries we used the **inscope** collection but to get overall numbers of blocked videos we used the **noduplicates** collection.

Some collections are missing if they had no results, for example Canada did not have any results for inscope missing communities results so ***CA_communities_inscope.csv*** is not in this repository.

There is also a ***messages.csv*** file that shows all unique messages presented to users, whether they are errors or block justifications.

## Columns

A general guide line to the values in the columns is the following:

* **url** - The URL in question that is missing from the search results in the country code.
* **title** - The title of the page that is missing from the search results, for example the HTML title of a video page.
* **error** - A message returned to user (for example a block justification or error) when they access the page from the country.
* **desktop_error** - Same as error, but shown to desktop users.
* **author** - The author of the URL if that were a personal account, this is a link to the VK profile itself.
* **author_error** - If visiting the authors page presents a message (for example a block justification) this is the message.
* **group_author** - If the URL is posted by a group or community this field is set.
* **group_author_error** - If visiting the group that posted the URL presents a message (for example a block justification).
* **message** - This is a meta column that presents the author_error first if present, followed by group_author_error, or error.
* **case_date** - If the message presented to users mentioned a case date this field is set.


## License

All data is provided under Creative Commons
Attribution-NonCommercial-ShareAlike 4.0 International and available in full
[here](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode) and summarized
[here](https://creativecommons.org/licenses/by-nc-sa/4.0/).
