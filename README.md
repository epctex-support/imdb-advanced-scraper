[https://apify.com/epctex/imdb-advanced-scraper](https://apify.com/epctex/imdb-advanced-scraper?fpr=yhdrb)

# Actor - IMDB Advanced Scraper

## IMDB Advanced scraper

Since IMDB doesn't provide a good and free API, this actor should help you to retrieve data from it. This actor can provide you with very detailed output from IMDB.

The IMDB Advanced data scraper supports the following features:

-   Search any keyword - You can search any keyword you would like to have and get the results.

-   Scrape lists - Scrape any list that you'd like to get from IMDB

-   Scrape any search result - You can search for keywords, artists, movies, companies, and many more!

-   Scrape genres - If you want to get the most read books on a certain category or anything related to the genres, just type the URL.

-   Scrape movie detail - Scrape very detailed information for each of the movies that you'd like to get.

-   Scrape artist detail - Scrape any artist and their information.

## What are the advantages of this actor compared to others?
This actor is extremely optimized, very fast, and provides at least 5x more data than the other actors or projects that you might experience.

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/imdb-advanced-scraper/issues).

## Input Parameters

The input of this scraper should be JSON containing the list of pages on IMDB that should be visited. Possible fields are:

- `search`: (Optional) (String) Keyword that you want to search on IMDB.

- `mode`: (Optional) (String) Mode of search. This attribute has to be initiated when a search keyword is provided. The options are: `all`, `tt` (Titles), `ep` (TV Episodes),`nm` (Names),`co` (Companies),`kw` (Keywords).

- `startUrls`: (Optional) (Array) List of IMDB URLs. You should only provide a list, title, name, search and find URLs.

- `endPage`: (Optional) (Number) Final number of page that you want to scrape. The default is `Infinite`. This applies to all `search` requests and `startUrls` individually.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

- `extendOutputFunction`: (Optional) (String) Function that takes a JQuery handle ($) as an argument and returns an object with data.

- `customMapFunction`: (Optional) (String) Function that takes each object's handle as an argument and returns the object with executing the function.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Tip

When you want to have a scrape over a specific item URL, just copy and paste the link as one of the **startUrl**.

If you would like to scrape only the first page of a list then put the link for the page and have the `endPage` as 1.

With the last approach that is explained above you can also fetch any interval of pages. If you provide the 5th page of a list and define the `endPage` parameter as 6 then you'll have the 5th and 6th pages only.

### Compute Unit Consumption

The actor is optimized to run blazing fast and scrape many items as possible. Therefore, it forefronts all item detail requests. If the actor doesn't block very often it'll scrape 100 items in 1 minute with ~0.03-0.06 compute units.

### IMDB Advanced Scraper Input example

```json
{
  "searchUrls":[
    "https://www.imdb.com/title/tt0056234/?ref_=adv_li_tt",
    "https://www.imdb.com/name/nm0912504/?ref_=fn_al_nm_1",
    "https://www.imdb.com/list/ls016522954/?ref_=nv_tvv_dvd",
    "https://www.imdb.com/find?s=kw&q=warn&ref_=nv_sr_sm"
  ],
  "proxy":{
    "useApifyProxy":true
  },
  "search":"warner bro",
  "mode": "all",
  "maxItems":20
}
```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## IMDB Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this IMDB Advanced actor.

## Scraped IMDB Properties

The structure of each item in IMDB looks like this:

### Title Item Detail

```json
{
  "id": "tt18138670",
  "productionStatus": {
    "currentProductionStage": {
      "id": "released",
      "text": "Released"
    },
    "productionStatusHistory": [
      {
        "status": {
          "id": "released",
          "text": "Released"
        }
      }
    ],
    "restriction": null
  },
  "canHaveEpisodes": false,
  "series": {
    "series": {
      "runtime": null
    }
  },
  "titleText": {
    "text": "Kurt Warner on Mac Jones, cerebral QBs & the state of quarterback play in 2021"
  },
  "titleType": {
    "id": "podcastEpisode"
  },
  "originalTitleText": {
    "text": "Kurt Warner on Mac Jones, cerebral QBs & the state of quarterback play in 2021"
  },
  "certificate": null,
  "releaseYear": {
    "year": 2021
  },
  "releaseDate": {
    "day": 15,
    "month": 12,
    "year": 2021,
    "country": {
      "id": "NO",
      "text": "Norway"
    }
  },
  "runtime": null,
  "canRate": {
    "isRatable": true
  },
  "ratingsSummary": {
    "topRanking": null
  },
  "meterRanking": null,
  "primaryImage": null,
  "images": {
    "total": 0
  },
  "videos": {
    "total": 0
  },
  "primaryVideos": [],
  "externalLinks": {
    "total": 0
  },
  "metacritic": null,
  "keywords": [],
  "genres": {
    "genres": []
  },
  "plot": null,
  "plotContributionLink": {
    "url": "https://contribute.imdb.com/updates?update=tt18138670:outlines.add.1.locale~en-US"
  },
  "credits": {
    "total": 0
  },
  "principalCredits": [],
  "reviews": {
    "total": 0
  },
  "criticReviewsTotal": {
    "total": 0
  },
  "triviaTotal": {
    "total": 0
  },
  "meta": {
    "canonicalId": "tt18138670",
    "publicationStatus": "PUBLISHED"
  },
  "castPageTitle": [],
  "creatorsPageTitle": [],
  "directorsPageTitle": [],
  "countriesOfOrigin": null,
  "production": [],
  "featuredReviews": [],
  "wins": {
    "total": 0
  },
  "nominations": {
    "total": 0
  },
  "prestigiousAwardSummary": null,
  "episodes": null,
  "videoStrip": [],
  "titleMainImages": [],
  "imageUploadLink": {
    "url": "https://contribute.imdb.com/image/tt18138670/add?bus=imdb&return_url=https%3A%2F%2Fwww.imdb.com%2Fclose_me&site=web"
  },
  "cast": [],
  "principalCast": [],
  "creators": [],
  "directors": [],
  "writers": [],
  "trivia": [],
  "goofsTotal": {
    "total": 0
  },
  "goofs": [],
  "quotesTotal": {
    "total": 0
  },
  "quotes": [],
  "crazyCredits": [],
  "alternateVersions": [],
  "connections": [],
  "soundtrack": [],
  "iframeAddReviewLink": {
    "url": "https://contribute.imdb.com/review/tt18138670/add?bus=imdb&return_url=https%3A%2F%2Fwww.imdb.com%2Fclose_me&site=web"
  },
  "faqsTotal": {
    "total": 0
  },
  "faqs": [],
  "detailsExternalLinks": [],
  "spokenLanguages": null,
  "akas": [],
  "filmingLocations": [],
  "companies": {
    "total": 0
  },
  "productionBudget": null,
  "lifetimeGross": null,
  "openingWeekendGross": null,
  "worldwideGross": null,
  "technicalSpecifications": {
    "soundMixes": {
      "items": []
    },
    "aspectRatios": {
      "items": []
    },
    "colorations": {
      "items": []
    }
  },
  "contributionQuestions": []
}
```

### Name Item Detail

```json
{
  "url": "https://www.imdb.com/name/nm0912504/?ref_=fn_al_nm_1",
  "name": "John Warner",
  "mainImage": "https://m.media-amazon.com/images/M/MV5BNzE2NDg4NTY0MF5BMl5BanBnXkFtZTgwOTI2NTcxODE@._V1_UX214_CR0,0,214,317_AL_.jpg",
  "starmeter": {
    "rank": "SEE RANK",
    "change": "Up 889,249 this week"
  },
  "bio": "Contribute to IMDb. Add a bio, trivia, and more.\n            Update information for John Warner »",
  "birthDate": "1969-2-10",
  "birthPlace": "Richmond, Indiana, USA",
  "knownFor": [
    {
      "title": "For All Mankind",
      "role": "Camera and Electrical Department",
      "year": "2021-2022",
      "image": "https://m.media-amazon.com/images/M/MV5BZDMwODYyM2ItZjNlYi00YzAzLTliODItYWFkOWJiMzVhOTY0XkEyXkFqcGdeQXVyMTkxNjUyNQ@@._V1_UX148_CR0,0,148,216_AL_.jpg",
      "url": "https://www.imdb.com/title/tt7772588/?ref_=nm_knf_t1"
    },
    {
      "title": "Phone Booth",
      "role": "Camera and Electrical Department",
      "year": "2002",
      "image": "https://m.media-amazon.com/images/M/MV5BMTcxNDQ5MzAyOV5BMl5BanBnXkFtZTYwMjkxMTU3._V1_UX148_CR0,0,148,216_AL_.jpg",
      "url": "https://www.imdb.com/title/tt0183649/?ref_=nm_knf_t2"
    },
    {
      "title": "From Dusk Till Dawn",
      "role": "Visual Effects",
      "year": "1996",
      "image": "https://m.media-amazon.com/images/M/MV5BZjk3YmZhMDAtOWUzMS00YjE5LTkxNzAtY2I1NGZjMDA2ZTk0XkEyXkFqcGdeQXVyMTQxNzMzNDI@._V1_UX148_CR0,0,148,216_AL_.jpg",
      "url": "https://www.imdb.com/title/tt0116367/?ref_=nm_knf_t3"
    },
    {
      "title": "The Jungle Book",
      "role": "Camera and Electrical Department",
      "year": "2016",
      "image": "https://m.media-amazon.com/images/M/MV5BMTc3NTUzNTI4MV5BMl5BanBnXkFtZTgwNjU0NjU5NzE@._V1_UX148_CR0,0,148,216_AL_.jpg",
      "url": "https://www.imdb.com/title/tt3040964/?ref_=nm_knf_t4"
    }
  ],
  "filmography": [
    {
      "title": "For All MankindEpisode #3.10Episode #3.9Episode #3.8Episode #3.7Episode #3.6",
      "date": "2021-2022",
      "url": "https://www.imdb.com/title/tt7772588/?ref_=nm_flmg_cam_1"
    },
    {
      "title": "Combat ShipsGame Changers",
      "date": "2022",
      "url": "https://www.imdb.com/title/tt7174736/?ref_=nm_flmg_cam_2"
    },
    {
      "title": "Eternals",
      "date": "2021",
      "url": "https://www.imdb.com/title/tt9032400/?ref_=nm_flmg_cam_3"
    },
    {
      "title": "The Morning ShowKill the Fatted CalfLauraIt's Like the Flu",
      "date": "2021",
      "url": "https://www.imdb.com/title/tt7203552/?ref_=nm_flmg_cam_4"
    },
    {
      "title": "Terminator: Dark Fate",
      "date": "2019",
      "url": "https://www.imdb.com/title/tt6450804/?ref_=nm_flmg_cam_5"
    },
    {
      "title": "SchooledGlascott MascotDarth MellorKris Kross",
      "date": "2019",
      "url": "https://www.imdb.com/title/tt6546758/?ref_=nm_flmg_cam_6"
    },
    {
      "title": "The GoldbergsEight-bit GoldbergsThe Beverly Goldberg CookbookOur Perfect StrangersThere Can Be Only One Highlander ClubMy Valentine Boy",
      "date": "2018-2019",
      "url": "https://www.imdb.com/title/tt2712740/?ref_=nm_flmg_cam_7"
    },
    {
      "title": "Venom",
      "date": "2018",
      "url": "https://www.imdb.com/title/tt1270797/?ref_=nm_flmg_cam_8"
    },
    {
      "title": "El Chicano",
      "date": "2018",
      "url": "https://www.imdb.com/title/tt7374952/?ref_=nm_flmg_cam_9"
    },
    {
      "title": "Run for Your Life",
      "date": "2018",
      "url": "https://www.imdb.com/title/tt7657698/?ref_=nm_flmg_cam_10"
    },
    {
      "title": "The Get",
      "date": "2017",
      "url": "https://www.imdb.com/title/tt6466902/?ref_=nm_flmg_cam_11"
    },
    {
      "title": "BonesThe Final Chapter: The End in the EndThe Day in the LifeThe Radioactive Panthers in the PartyThe Steal in the WheelsThe Grief and the Girl",
      "date": "2015-2017",
      "url": "https://www.imdb.com/title/tt0460627/?ref_=nm_flmg_cam_12"
    },
    {
      "title": "The Jungle Book",
      "date": "2016",
      "url": "https://www.imdb.com/title/tt3040964/?ref_=nm_flmg_cam_13"
    },
    {
      "title": "PreacherPilot",
      "date": "2016",
      "url": "https://www.imdb.com/title/tt5016504/?ref_=nm_flmg_cam_14"
    },
    {
      "title": "ColonyPilot",
      "date": "2016",
      "url": "https://www.imdb.com/title/tt4209256/?ref_=nm_flmg_cam_15"
    },
    {
      "title": "The Adversaries",
      "date": "2015",
      "url": "https://www.imdb.com/title/tt4428006/?ref_=nm_flmg_cam_16"
    },
    {
      "title": "The Red Thunder",
      "date": "2015",
      "url": "https://www.imdb.com/title/tt4151892/?ref_=nm_flmg_cam_17"
    },
    {
      "title": "Web TherapyJudicial OversightDrink to ForgetSmile Through the PainTrust ExerciseAffairs to Remember",
      "date": "2013-2014",
      "url": "https://www.imdb.com/title/tt1930123/?ref_=nm_flmg_cam_18"
    },
    {
      "title": "Horrible Bosses 2",
      "date": "2014",
      "url": "https://www.imdb.com/title/tt2170439/?ref_=nm_flmg_cam_19"
    },
    {
      "title": "TwistedA Tale of Two ConfessionsDanny, InterruptedYou're a Good Man, Charlie McBrideThe Son also FallsDanny Indemnity",
      "date": "2013-2014",
      "url": "https://www.imdb.com/title/tt2355844/?ref_=nm_flmg_cam_20"
    },
    {
      "title": "SuburgatoryThe Birds and the BiedermanOpen Door PolicyVictor HaNo Me Gusta, Mami",
      "date": "2014",
      "url": "https://www.imdb.com/title/tt1741256/?ref_=nm_flmg_cam_21"
    },
    {
      "title": "Trophy Wife",
      "date": "2013",
      "url": "https://www.imdb.com/title/tt2400736/?ref_=nm_flmg_cam_22"
    },
    {
      "title": "Pacific Rim",
      "date": "2013",
      "url": "https://www.imdb.com/title/tt1663662/?ref_=nm_flmg_cam_23"
    },
    {
      "title": "Web TherapySpritzer SurpriseHatching a PlanPenetratressCloser When We're ApartLosing Followers",
      "date": "2013",
      "url": "https://www.imdb.com/title/tt1343865/?ref_=nm_flmg_cam_24"
    },
    {
      "title": "Lovestruck: The Musical",
      "date": "2013",
      "url": "https://www.imdb.com/title/tt2246673/?ref_=nm_flmg_cam_25"
    },
    {
      "title": "How to Live with Your Parents (for the Rest of Your Life)",
      "date": "2013",
      "url": "https://www.imdb.com/title/tt2226397/?ref_=nm_flmg_cam_26"
    },
    {
      "title": "WeedsIt's Time, Part 2It's Time, Part 1God Willing and the Creek Don't RiseThresholdSaplings",
      "date": "2005-2012",
      "url": "https://www.imdb.com/title/tt0439100/?ref_=nm_flmg_cam_27"
    },
    {
      "title": "The Amazing Spider-Man",
      "date": "2012",
      "url": "https://www.imdb.com/title/tt0948470/?ref_=nm_flmg_cam_28"
    },
    {
      "title": "Little in Common",
      "date": "2011",
      "url": "https://www.imdb.com/title/tt1822247/?ref_=nm_flmg_cam_29"
    },
    {
      "title": "Man Up!",
      "date": "2011",
      "url": "https://www.imdb.com/title/tt1828238/?ref_=nm_flmg_cam_30"
    },
    {
      "title": "CSI: NYShop Till You DropOut of the SkyDamned If You DoUnfriendly Chat",
      "date": "2010",
      "url": "https://www.imdb.com/title/tt0395843/?ref_=nm_flmg_cam_31"
    },
    {
      "title": "Parks and RecreationFreddy SpaghettiThe Master PlanTelethon94 MeetingsSummer Catalog",
      "date": "2009-2010",
      "url": "https://www.imdb.com/title/tt1266020/?ref_=nm_flmg_cam_32"
    },
    {
      "title": "Worst WeekThe PartyThe EpiduralThe SexThe PuppyThe Article",
      "date": "2008-2009",
      "url": "https://www.imdb.com/title/tt1197632/?ref_=nm_flmg_cam_33"
    },
    {
      "title": "Better Off Ted",
      "date": "2009",
      "url": "https://www.imdb.com/title/tt1235547/?ref_=nm_flmg_cam_34"
    },
    {
      "title": "The Apostles",
      "date": "2008",
      "url": "https://www.imdb.com/title/tt0948744/?ref_=nm_flmg_cam_35"
    },
    {
      "title": "The More Things Change...",
      "date": "2008",
      "url": "https://www.imdb.com/title/tt1131739/?ref_=nm_flmg_cam_36"
    },
    {
      "title": "The Day the Earth Stood Still",
      "date": "2008",
      "url": "https://www.imdb.com/title/tt0970416/?ref_=nm_flmg_cam_37"
    },
    {
      "title": "The OaksPilot",
      "date": "2008",
      "url": "https://www.imdb.com/title/tt1082514/?ref_=nm_flmg_cam_38"
    },
    {
      "title": "12 Miles of Bad RoadPilot",
      "date": "2008",
      "url": "https://www.imdb.com/title/tt0804432/?ref_=nm_flmg_cam_39"
    },
    {
      "title": "Law Dogs",
      "date": "2007",
      "url": "https://www.imdb.com/title/tt0847179/?ref_=nm_flmg_cam_40"
    },
    {
      "title": "The Untitled Rob Roy Thomas Project",
      "date": "2007",
      "url": "https://www.imdb.com/title/tt0960873/?ref_=nm_flmg_cam_41"
    },
    {
      "title": "InsatiablePilot",
      "date": "2007",
      "url": "https://www.imdb.com/title/tt0901196/?ref_=nm_flmg_cam_42"
    },
    {
      "title": "Boys LifePilot",
      "date": "2006",
      "url": "https://www.imdb.com/title/tt0779794/?ref_=nm_flmg_cam_43"
    },
    {
      "title": "HeistPilot",
      "date": "2006",
      "url": "https://www.imdb.com/title/tt0491281/?ref_=nm_flmg_cam_44"
    },
    {
      "title": "Head CasesBe Your Best YouIn the ClubMalpractice Makes PerfectS(elf) HelpEpisode #1.5",
      "date": "2005",
      "url": "https://www.imdb.com/title/tt0460645/?ref_=nm_flmg_cam_45"
    },
    {
      "title": "War of the Worlds",
      "date": "2005",
      "url": "https://www.imdb.com/title/tt0407304/?ref_=nm_flmg_cam_46"
    },
    {
      "title": "Zathura: A Space Adventure",
      "date": "2005",
      "url": "https://www.imdb.com/title/tt0406375/?ref_=nm_flmg_cam_47"
    },
    {
      "title": "The InsideNew Girl in Town",
      "date": "2005",
      "url": "https://www.imdb.com/title/tt0412148/?ref_=nm_flmg_cam_48"
    },
    {
      "title": "Taxi",
      "date": "2004/I",
      "url": "https://www.imdb.com/title/tt0316732/?ref_=nm_flmg_cam_49"
    },
    {
      "title": "Dr. VegasPilot",
      "date": "2004",
      "url": "https://www.imdb.com/title/tt0410978/?ref_=nm_flmg_cam_50"
    },
    {
      "title": "The Big Wide World of Carl Laemke",
      "date": "2003",
      "url": "https://www.imdb.com/title/tt0366234/?ref_=nm_flmg_cam_51"
    },
    {
      "title": "The O.C.The RescueThe EscapeThe GirlfriendThe OutsiderThe Debut",
      "date": "2003",
      "url": "https://www.imdb.com/title/tt0362359/?ref_=nm_flmg_cam_52"
    },
    {
      "title": "Old School",
      "date": "2003",
      "url": "https://www.imdb.com/title/tt0302886/?ref_=nm_flmg_cam_53"
    },
    {
      "title": "Phone Booth",
      "date": "2002",
      "url": "https://www.imdb.com/title/tt0183649/?ref_=nm_flmg_cam_54"
    },
    {
      "title": "Megiddo: The Omega Code 2",
      "date": "2001",
      "url": "https://www.imdb.com/title/tt0263728/?ref_=nm_flmg_cam_55"
    },
    {
      "title": "American Pie 2",
      "date": "2001",
      "url": "https://www.imdb.com/title/tt0252866/?ref_=nm_flmg_cam_56"
    },
    {
      "title": "Blonde",
      "date": "2001",
      "url": "https://www.imdb.com/title/tt0254890/?ref_=nm_flmg_cam_57"
    },
    {
      "title": "Red Planet",
      "date": "2000",
      "url": "https://www.imdb.com/title/tt0199753/?ref_=nm_flmg_cam_58"
    },
    {
      "title": "Men of Honor",
      "date": "2000",
      "url": "https://www.imdb.com/title/tt0203019/?ref_=nm_flmg_cam_59"
    },
    {
      "title": "Galaxy Quest",
      "date": "1999",
      "url": "https://www.imdb.com/title/tt0177789/?ref_=nm_flmg_cam_60"
    },
    {
      "title": "Stuart Little",
      "date": "1999",
      "url": "https://www.imdb.com/title/tt0164912/?ref_=nm_flmg_cam_61"
    },
    {
      "title": "Teaching Mrs. Tingle",
      "date": "1999",
      "url": "https://www.imdb.com/title/tt0133046/?ref_=nm_flmg_cam_62"
    },
    {
      "title": "SlidersRevelationsRoads TakenThe ChasmMy Brother's KeeperWay Out West",
      "date": "1998-1999",
      "url": "https://www.imdb.com/title/tt0112167/?ref_=nm_flmg_cam_63"
    },
    {
      "title": "Omega Boost",
      "date": "1999",
      "url": "https://www.imdb.com/title/tt0457425/?ref_=nm_flmg_cam_64"
    },
    {
      "title": "Baby Geniuses",
      "date": "1999",
      "url": "https://www.imdb.com/title/tt0118665/?ref_=nm_flmg_cam_65"
    },
    {
      "title": "Susan's Plan",
      "date": "1998",
      "url": "https://www.imdb.com/title/tt0145505/?ref_=nm_flmg_cam_66"
    },
    {
      "title": "Slums of Beverly Hills",
      "date": "1998",
      "url": "https://www.imdb.com/title/tt0120831/?ref_=nm_flmg_cam_67"
    },
    {
      "title": "Jackie Brown",
      "date": "1997",
      "url": "https://www.imdb.com/title/tt0119396/?ref_=nm_flmg_cam_68"
    },
    {
      "title": "Nightwatch",
      "date": "1997",
      "url": "https://www.imdb.com/title/tt0119791/?ref_=nm_flmg_cam_69"
    },
    {
      "title": "Babylon 5Z'ha'dumShadow DancingAnd the Rock Cried Out, No Hiding PlaceGrey 17 Is MissingWalkabout",
      "date": "",
      "url": "https://www.imdb.com/title/tt0105946/?ref_=nm_flmg_cam_70"
    },
    {
      "title": "Timemaster",
      "date": "1995",
      "url": "https://www.imdb.com/title/tt0114676/?ref_=nm_flmg_cam_71"
    },
    {
      "title": "Siringo",
      "date": "1995",
      "url": "https://www.imdb.com/title/tt0111202/?ref_=nm_flmg_cam_72"
    },
    {
      "title": "Gunfight at Red Dog Corral",
      "date": "1993",
      "url": "https://www.imdb.com/title/tt0205994/?ref_=nm_flmg_cam_73"
    },
    {
      "title": "Killing Zoe",
      "date": "1993",
      "url": "https://www.imdb.com/title/tt0110265/?ref_=nm_flmg_cam_74"
    },
    {
      "title": "Precious Victims",
      "date": "1993",
      "url": "https://www.imdb.com/title/tt0107869/?ref_=nm_flmg_cam_75"
    },
    {
      "title": "Illusions",
      "date": "1992",
      "url": "https://www.imdb.com/title/tt0104487/?ref_=nm_flmg_cam_76"
    },
    {
      "title": "Likely Suspects",
      "date": "1992",
      "url": "https://www.imdb.com/title/tt0103475/?ref_=nm_flmg_cam_77"
    },
    {
      "title": "Mad at the Moon",
      "date": "1992",
      "url": "https://www.imdb.com/title/tt0104787/?ref_=nm_flmg_cam_78"
    },
    {
      "title": "Invasion of Privacy",
      "date": "1992",
      "url": "https://www.imdb.com/title/tt0104526/?ref_=nm_flmg_cam_79"
    },
    {
      "title": "The Cell",
      "date": "2000",
      "url": "https://www.imdb.com/title/tt0209958/?ref_=nm_flmg_vsl_1"
    },
    {
      "title": "Spawn",
      "date": "1997",
      "url": "https://www.imdb.com/title/tt0120177/?ref_=nm_flmg_vsl_2"
    },
    {
      "title": "From Dusk Till Dawn",
      "date": "1996",
      "url": "https://www.imdb.com/title/tt0116367/?ref_=nm_flmg_vsl_3"
    }
  ],
  "jobCategories": [],
  "overview": [
    {
      "label": "Born",
      "value": "February 10, 1969 in Richmond, Indiana, USA"
    },
    {
      "label": "Nicknames",
      "value": "djub, JWJDUBWarnerIndiana JohnIndy"
    }
  ],
  "miniBio": "",
  "family": [
    {
      "label": "Spouse",
      "members": []
    }
  ],
  "salary": []
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
