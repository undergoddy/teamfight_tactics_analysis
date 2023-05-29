![python](https://img.shields.io/badge/python-3.5%20%7C%203.6%20%7C%203.7-blue)
![TFT](https://img.shields.io/badge/game-Teamfight%20Tactics-yellowgreen)

# Teamfight Tactics extraction and parsing via RiotApi

This project is made to gather and analyse TFT games data.

## Instruments
- Connection to Riot Api established via [riotwatcher](https://riot-watcher.readthedocs.io/en/latest/) lib
- Data transformation - pandas
- Utility - tqdm, json, requests

## What you need
- Python
- [RiotDeveloper](https://developer.riotgames.com/) account for api key

## How it works
- *tft_matches_data_extraction.ipynb* extracts data (it can be rather heavy, 60000 matches ~1.2GBs). API default limits are - 20 requests every 1 seconds(s), 100 requests every 2 minutes(s), so extraction can take some time. Matches data is preseneted in the form of heavy nested jsons(example in repo, use [jsonviewer](https://jsonviewer.stack.hu/) to read normally). Only challenger games for now.
- *matches_data_transformation.ipynb* parses useful data from a pile. I used simple python list/dict/set methods as they are simple and fast. Main functions parse augment placements, augments mean placement, character placements, character-item placement. All data have patch, region, set labels to choose from.

## What's next
I'm currently working on getting different leagues data, it takes a lot of time due to API rate limits. And data visualisation in Tableau.
