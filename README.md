
# OSP Ranking Data

This repository contains JSON dumps of the ranking results that are displayed in the [Open Syllabus Explorer](http://explorer.opensyllabusproject.org/) web application, to a maximum depth of 10,000 results.

The results for each of the individual fields, institutions, and states are broken out into a separate file. For example, this file:

[`/ranks/fields/english.json`](https://github.com/davidmcclure/osp-ranking-data/blob/master/ranks/fields/english.json)

Is a JSON dump of the top 10k results that get displayed if you go to the website and select "English" from the "Field" dropdown. The overall, un-filtered results are also included:

[`/ranks/overall.json`](https://github.com/davidmcclure/osp-ranking-data/blob/master/ranks/overall.json)

## Schema

In the data files, each text looks like this:

```json
  {
    "teaching_score": 1.0,
    "overall_count": 3934,
    "filtered_count": 3934,
    "journal": null,
    "identifier": "000668425-4",
    "date": "C1959",
    "author": "Strunk, William, 1869-1946",
    "overall_rank": 1,
    "id": "1305566",
    "type": "text",
    "title": "The Elements of Style"
  },
```

- **Teaching Score**: A 0-1 score (displayed as 0-100 on the site) that represents the texts position in the linear _ranking_ order defined by the overall citation counts.

- **Overall Count**: The total number of times that the text is assigned in the corpus.

- **Filtered Count**: The number of times the text is assigned within the current filter. Eg, a text might be assigned 1,000 times overall, but just 50 times on English syllabi.

- **Journal**: If the text is an article, the journal that the article was published in. Since most of the matches come from the Harvard Library Cloud collection (mostly monographs), this is usually empty.

- **Identifier**: A unique identifier for the text. For the Harvard records, these are the "control numbers" from the original MARC records. For JSTOR records, the JSTOR id.

- **Date**: A non-machine-readable date value, pulled directly from the MARC records.

- **Author**: The author (first author, for journal articles) of the resource.

- **Overall Rank**: The text's ranking order in the overall (unfiltered) results.

- **id**: The database id for the text. This is used to form the URLs for the text profile pages on the site. Eg, `1305566` for [The Elements of Style](http://explorer.opensyllabusproject.org/text/1305566).
