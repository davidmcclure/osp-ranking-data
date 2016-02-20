
# OSP Ranking Data

This repository contains JSON dumps of the ranking results that are displayed in the [Open Syllabus Explorer](http://explorer.opensyllabusproject.org/) web application, to a maximum depth of 10,000 results.

The results for each of the individual fields, institutions, and states are broken out into a separate file. For example, this file:

[`ranks/fields/english.json`](https://github.com/davidmcclure/osp-ranking-data/blob/master/ranks/fields/english.json)

Is a JSON dump of the top 10k results that get displayed if you go to the website and select "English" from the "Field" dropdown. The overall, un-filtered results are also included:

[`ranks/overall.json`](https://github.com/davidmcclure/osp-ranking-data/blob/master/ranks/overall.json)

If you make use of this data, please cite the [Open Syllabus Project](http://opensyllabusproject.org).

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

- **`teaching_score`**: A 0-1 score (displayed as 0-100 on the site) that represents the texts position in the linear _ranking_ order defined by the overall citation counts.

- **`overall_count`**: The total number of times that the text is assigned in the corpus.

- **`filtered_count`**: The number of times the text is assigned within the current filter. Eg, a text might be assigned 1,000 times overall, but just 50 times on English syllabi.

- **`journal`**: If the text is an article, the journal that the article was published in. Since most of the matches come from the Harvard Library Cloud collection (mostly monographs), this is usually empty.

- **`identifier`**: A canonical identifier for the text. For the Harvard records, these are the "control numbers" from the original MARC records. For JSTOR records, the JSTOR id.

- **`date`**: A non-machine-readable date value, pulled directly from the MARC records.

- **`author`**: The author (first author, for journal articles) of the resource.

- **`overall_rank`**: The text's ranking order in the overall (unfiltered) results.

- **`id`**: The database id for the text. This is used to form the URLs for the text profile pages on the site. Eg, `1305566` for [The Elements of Style](http://explorer.opensyllabusproject.org/text/1305566).

## Caveats

These rankings represent a fairly accurate snapshot of texts assigned _in the corpus of syllabi that we currently have_. But, of course - this is far from being a complete sample of all the syllabi out there in the world! What's more, the OSP corpus is what statisticians would call a "[convenience sample](https://en.wikipedia.org/wiki/Accidental_sampling)" - for the time being, we're only able to access syllabi that have been posted on public websites, which, for various reasons, might not be representative of all syllabi.

We're working on expanding the corpus in a couple of ways. We're planning to scrape more documents from the web, and we're also hoping to partner with universities to get access to archived collections of syllabi that aren't posted online. For now, though, it's important to keep in mind that this data is pulled from one particular subset of syllabi, and can't yet be considered a comprehensive authority on text assignment trends. (We're hoping to get there eventually.)

This is especially true for filtered result sets that are based on a relatively small number of citations. For example, we only extracted about 1,600 individual text assignments from syllabi assigned in Wyoming, a small fraction of the ~300k from Texas. This means that the Wyoming results aren't very meaningful at this point, since we just have a tiny (and very likely unrepresentative) sample. Generally speaking - the larger the numbers, the more valid it becomes to make high-level generalizations about the results.

---

<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License</a>.
