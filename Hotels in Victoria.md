# Hotels in Victoria

LOC entries:

* Hotels -- Victoria -- [Place]
* Bars (Drinking establishments) -- Victoria -- [Place]
* [Place] (Vic.) -- Hotels

[query](http://api.trove.nla.gov.au/result?q=subject:"Vic+hotels"+OR+subject:"Hotels+Victoria"+OR+subject:"Bars+drinking+establishments+victoria"&zone=picture&encoding=json&include=workversions&reclevel=full)

Loop through versions if we want multiple photos.

Use work id and LA id to get Bibtex citation that includes subjects.

[Bibtex](http://trove.nla.gov.au/work/167142222?citationFormat=BibTeX&selectedversion=NBD49193358)

Results:

```
@COMMENT { BibTex package created by Trove, National Library of Australia http://trove.nla.gov.au }
@Misc{ trove.nla.gov.au/work/167142222,
title = { Victoria Hotel, cnr. of Peel and Victoria Streets, North Melbourne, [Vic.] },
author = { Caldwell, Colin },
url = { http://handle.slv.vic.gov.au/10381/72426 },
year = { 1949 },
type = { Photograph },
subjects = { Victoria Hotel (N. Melbourne, Vic.); Bars (Drinking establishments) -- Victoria -- North Melbourne; North Melbourne (Vic.) -- Buildings, structures, etc; Melbourne (Vic.) -- History -- 1945-1965; Victoria Hotel Victoria Australia pubs North Melbourne },
note = { Photographer's name and information, including handwritten lists identifying buildings some with dates, supplied by photographer },
catalogue-url = { http://trove.nla.gov.au/work/167142222 }
}
```

* Parse subjects for places
* Geocode places

Can also download big versions of some photos (construct urls for Tarkine)