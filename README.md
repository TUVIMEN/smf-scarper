# smf-scraper

A bash script for scraping smf forums in json.

## Requirements

 - [reliq](https://github.com/TUVIMEN/reliq)
 - [jq](https://github.com/stedolan/jq)

## Installation
    
    install -m 755 smf-scraper /usr/bin

## Supported links formats

    http(s)?://forum.com/.*([?/&;]topic[=,]|-t)([[:digit:]]+).*
    http(s)?://forum.com/.*([?/&;]board[=,])([[:digit:]]+).*
    http(s)?://forum.com/?(*/)index.php.*
    http(s)?://forum.com.*

## Json format

Here's example of [topic1](topic1-example.json) and [topic2](topic2-example.json).

## Supported smf 1.x examples

    https://bitcointalk.org/
    https://forum.ipfon.pl/
    https://forumszkolne.pl/
    http://750mm.pl/

## Supported smf 2.0.x examples

    https://forums.soldat.pl/index.php?action=forum
    https://www.chemicalforums.com/index.php
    https://www.nukeworker.com/forum/index.php
    https://forum.nasm.us/
    https://forum.coppermine-gallery.net/
    https://www.norotors.com/index.php
    https://forums.camerabits.com/
    https://czfirearms.us
    https://www.theflatearthsociety.org/forum/index.php?wwwRedirect
    https://www.tropicalfishforums.co.uk/index.php?action=forum
    https://forum.kuntsevo.com/
    https://naijacrux.com/index.php
    https://arizonagunowners.com/
    http://bagnasadobre.org.pl/

## Supported smf 2.1.x examples

    https://forums.cadillaclasalle.club/
    https://tardisbuilders.com/
    https://forums.cyotek.com/
    https://tigerpedia.tigertms.com/
    https://forums.2000ad.com/
    https://aleforum.pl/

## Usage

    smf-scraper [URL]...

Script downloads topic to files named by their id's.

Script automatically recognizes version of forums but you can force it by using --topic1 --topic2 --forum1 --forum2 options followed by link.

Download forum into current directory using 4 processes

    smf-scraper -p 4 'https://forum.nasm.us/'

Download topic by irregular topic url into DIR 

    smf-scraper -d DIR -t 'https://forums.cyotek.com/cyotek-copytools/thanks/'

Download forum forcing 1.x version

    smf-scraper --forum1 'https://bitcointalk.org/index.php?board=1.0'

Get some help

    smf-scraper -h
