
# OSP Ranking Data

This repository contains JSON dumps of the ranking results that are displayed in the [Open Syllabus Explorer](http://explorer.opensyllabusproject.org/) web application, to a maximum depth of 10,000 results.

The results for each of the individual fields, institutions, and states are broken out into a separate file. For example, this file:

[`/ranks/fields/english.json`](https://github.com/davidmcclure/osp-ranking-data/blob/master/ranks/fields/english.json)

Is a JSON dump of the top 10k results that get displayed if you go to the website and select "English" from the "Field" dropdown. The overall, un-filtered results are also included:

[`/ranks/overall.json`](https://github.com/davidmcclure/osp-ranking-data/blob/master/ranks/overall.json)

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
