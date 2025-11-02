# Usenet Beginner's Guide
A guide to Usenet. If you have any questions, problems, or suggestions for improvement, feel free to create an issue or pull request!

## Status of the guide
The first part of the guide is complete; all that's missing is automation with Radarr & Sonarr—this will follow in the next few days.

## Last updated: September 19, 2025

---

### Understanding Usenet

Usenet was originally developed in the 1980s as a global, distributed discussion forum for text messages. Today, however, it is mainly used for sharing files.

File sharing on Usenet works by uploading files to “newsgroups.” The file is split into thousands of small files, which are then posted as “text” on Usenet. Once a file is uploaded, it is replicated on Usenet servers worldwide and can be downloaded by anyone who has access to these servers.

---

### Important terms

- **Usenet providers**: Providers that enable access to Usenet servers. Storage periods typically vary between 5 and 15+ years.

- **Usenet indexers**: These are search engines for Usenet. Since almost all uploads are encrypted nowadays, indexers are essential because without them, you can no longer find files.

- **NZB files**: A “recipe” or “treasure map” for your downloader. They tell the downloader how to download and reconstruct the encrypted file, which is split into thousands of small pieces (“postings”) from Usenet.

---

### Tools

- **Downloader**: **SABnzbd** accepts NZB files and downloads the actual files.

These tools are optional and will be discussed in more detail later:

- **Automation**: **Radarr** (for movies), **Sonarr** (for series), and **Prowlarr** (indexer management) can automate the download process.

- **Streaming**: With **Jellyfin**, you can run your own streaming service.

- **Jellyseerr**: With **Jellyseerr**, you can discover movies and series in a beautiful user interface and request them automatically with a single click.

---

### Preparation

#### 1. **Usenet provider**:

   - **For regular users**: **Ewaka** offers access to uploads that are up to 15+ years old.  
With this [promotional link](https://www.eweka.nl/en/landing/special-deal-evm-1), it costs only $2.50/month for the first year and then increases to $5.99/month. If you just want to try it out for a month, visit the [Ewaka homepage](https://www.eweka.nl/en).

   - **For occasional users**: A block account allows you to purchase a certain amount of data and use it without any time pressure. At **newsgroupdirect.com**, you can get 2 TB for $16 or 4 TB for $25. See the bottom of the page: [Usenet offers](https://newsgroupdirect.com/usenet-deals). Note that the retention period here is a maximum of 12 years, but block accounts with a retention period of 15+ years often cost 5-10 times more. It shouldn't make much difference, but it's worth mentioning. **Attention**: Immediately after purchase, your access data will be displayed, which you will not be able to access afterwards – so it's best to save it right away!

   - **Note: Since the providers' offers change very frequently, you are also welcome to write to me and ask for the best current deals. [Contact & Support](#contact--support)**.  
There is also a [list of provider deals](https://rexum.space/p/usenet-provider-deals/) from [rexum](https://rexum.space). The quality of Usenet providers varies greatly. Before you sign up for a particular deal, it's worth doing some research or [asking for more information](#contact--support) .

#### 2. **Usenet indexers**:

Note: I am not linking to any indexers here, but if you search for them, they should all be the first Google hits ;)

For German productions, German dubbing, and so-called “German DL” releases (DL = dual language, i.e., German + original soundtrack), there is really only one Usenet indexer: **SceneNZBs**.

For occasional users, indexers can often be used completely free of charge. However, if you want to download a lot or even automatically, you will have to pay an annual fee of €10-20.

Here is my indexer recommendation with a ranking based on my own experience. SceneNZBs is perfectly adequate to start with. The other indexers have significantly less German content, but sometimes they have older releases that are not (yet) available on SceneNZBs. They also often have English content earlier and in more variants.

| Rank | Indexer       | Free downloads/day       | Premium per year       | Registration open      |      Deletion of free accounts due to inactivity | Further info|
|------|---------------|--------------------------|------------------------|------------------------|--------------------------------------------------|--------------|
| 1.   | SceneNZBs | 5                            | 15 (10€ from the third year onwards) | Permanent              | 1 year                                            | Indispensable for German content – this indexer specializes in it.                      |
| 2.   | NewzBay | 30-day trial period, then 0   | 10€                    | Closed (user invites possible)       | 180 days | A new, modern indexer specializing in German content. Very good for anime (German dubbing & original with subtitles). Compared to SceneNZBs, however, it still lacks a larger archive of older material – but requests for missing content are fulfilled quickly. The perfect complement to SceneNZBs. |
| 3.   | NZBFinder     | 3                        | $15-45                 | Permanent              | ?                                                  | Also a very good indexer with a lot of German content.                    |
| 4.   | NZB.life      | 0                        | $15                    | Permanent              | ?                                                  | Also a very good indexer with a lot of German content.
| 5.   | DrunkenSlug   | 5                        | 15-25€                 | Every few months       | ?                                                  | Also a very good indexer with a lot of German content, but a bit expensive compared to NzbGeek.                    |
| 6.   | NzbGeek       | One-time $15 to test   | $12                    | Permanent              | -                                                 | Very good addition to SceneNZBs, as it is inexpensive, open registration, and has some older German content available.                          |
| 7.   | AnimeTosho    | ∞                        | €0                     | Not necessary            | -                                                 | Free indexer for anime (but little German content)

NzbGeek and DrunkenSlug have a lot of overlap, which is why you really only need one of them, if any.

3. Downloader (Usenet client):

There are numerous download clients for Usenet, but the undisputed leader is **SABnzbd**. There are several reasons for this:

- **Open source**: The software is transparent and can be further developed and reviewed by the community.
  
- **Free**: SABnzbd is completely free to use.

- **Versatility**: It works flawlessly and is available for Windows, macOS, and Linux.

- **(For professionals)**: Since it is a web application, SABnzbd runs excellently as a Docker container.

**Download**: [SABnzbd Download](https://sabnzbd.org/downloads)

**Installation**: Run the installer and follow the instructions.

---

**Getting started with SABnzbd**

After installation, you can start SABnzbd by double-clicking the icon on your desktop or searching for it. When you start it, your default browser will open with the SABnzbd web application.

**Initial setup**:
| Image | Instructions |
|:----:|-----------|
| ![Wizard](https://github.com/PCJones/usenet-guide/blob/main/img/sabnzbd1.png?raw=true) | **Step 1:** Select “English” as the language and then click on “Start Wizard.” |
| ![Enter login details](https://github.com/PCJones/usenet-guide/blob/main/img/sabnzbd2.png?raw=true) | **Step 2:** Enter your Ewaka or Block account login details here. You should have received this information immediately after purchase and also by email. Ensure that the SSL option is enabled so that all downloads are encrypted. This eliminates the need for a VPN or similar. |
| ![Third step](https://github.com/PCJones/usenet-guide/blob/main/img/sabnzbd3.png?raw=true) | **Step 3:** The wizard recommends bookmarking the SABnzbd web interface (`http://127.0.0.1:8080/sabnzbd/`) in your browser. This is useful if SABnzbd is already running in the background. Alternatively, you can also start SABnzbd via the desktop icon or the program search. You may want to customize the paths for the temporary folder and the download folder, which is also possible here. Finally, all you have to do is click on “Show SABnzbd.” |
| ![SABnzbd interface](https://github.com/PCJones/usenet-guide/blob/main/img/sabnzbd4.png?raw=true) | You will now see the SABnzbd interface—that's it for the initial configuration! We recommend browsing through the SABnzbd settings at your convenience and familiarizing yourself with the options. But for now, you are ready to start downloading. |

---

### Download

If you've made it this far, you've done the hardest part. From here on out, it's really easy! All of the indexers I've mentioned look more or less the same, so you shouldn't have any major difficulties if you use different ones.

| Image | Description |
|------|--------------|
| ![Logging in to Indexer](https://github.com/PCJones/usenet-guide/blob/main/img/indexer1.png?raw=true) | 1. Log in to Indexer (e.g., SceneNZBs) |
| ![Search](https://github.com/PCJones/usenet-guide/blob/main/img/indexer2.png?raw=true) | 2. At the top right of the search bar, we can search for something, such as movies or series. |
| ![Search results](https://github.com/PCJones/usenet-guide/blob/main/img/indexer3.png?raw=true) | 3. In my case, I searched for Tatort and found all possible Tatort movies. If you are searching for specific episodes, e.g., season 2, episode 8, the search format is always “series name S02E08.” Here you will also find important information such as the file size, the upload date, and much more in the title, such as the original source (Blu-Ray, WEB, DVD, etc.) or the quality (720p, 1080p, 4k, etc.). I will explain later in more detail what exactly you can and should pay attention to. |
| ![View Series](https://github.com/PCJones/usenet-guide/blob/main/img/indexer4.png?raw=true) | 4. Tip: For movie series and especially TV series, most indexers have a button such as “View Series,” which gives you an organized overview of all available seasons, episodes, and releases. |
| ![Download or shopping cart](https://github.com/PCJones/usenet-guide/blob/main/img/indexer5.png?raw=true) | 5. Once we have decided on a release, most indexers give us two options: either we download the NZB file directly, or we add it to our “shopping cart.” This is useful if we want to download many files. If you add the releases to the shopping cart, you will find all added downloads under Profile->My Cart (or nearby, depending on the indexer). You can then select them all with one click to download them as a .zip file—this saves you from having dozens of individual .nzb files. You don't have to unzip the .zip file either, SABnzbd does that automatically for you. |
| ![Downloaded file](https://github.com/PCJones/usenet-guide/blob/main/img/downloadfolder1.png?raw=true) | 6. I have now downloaded one .nzb file, but there may be several (and, as mentioned, .zip files containing several .nzbs).
| ![SABnzbd Import](https://github.com/PCJones/usenet-guide/blob/main/img/sabnzbd4.png?raw=true) | 7. Now go to SABnzbd and either drag and drop the files into it or click on the large “Add NZB” button. |
| ![Download process](https://github.com/PCJones/usenet-guide/blob/main/img/sabnzbd5.png?raw=true) | 8. SABnzbd starts the download automatically. Once it is complete and unzipped, you will find the content in the specified download folder. That's it! :) |

---

### Important terms in the release name

The release name (e.g., something like “Game of Thrones S01E01 German EAC3 DL 1080p BluRay x265-VECTOR”) provides you with some important information.

At the very end, after the hyphen, you will always see the release group, i.e., the group that actually ripped the movie or episode from a BluRay or downloaded it from a streaming service. This may be interesting for some, but you can ignore it for now.

| Term            | Explanation                                                                                                                                                                                                                        |
|--------------------|------------------------------------------------------------- ---------------------------------------------------------------------------------------------------- ---------------------------------------------------------------------------------------- -|
| x264, h264         | Codec for video compression. It creates files that are larger than x265, but offers better compatibility with older devices. Recommended for 720p and 1080p and high quality requirements. |
| x265, h265, HEVC   | High Efficiency Video Coding (HEVC), often referred to as h.265 or x265, is a more modern codec that compresses videos to about half the file size of h.264, but with the same quality. Ideal for 4K videos or when storage space is limited.    |
| 720p, 1080p, 2160p | Quality of the release. 720p = HD, 1080p = Full HD, 2160p = 4K Ultra HD.                                                                                                                                                                                 |
| German             | The release has a German audio track.                                                                                                                                                                                 |
| German DL          | Dual Language - The release is bilingual, usually German and the original language. The DL may also appear later in the file name, e.g. “German EAC3 DL”.                                                                                         |
| WEB-DL             | The source comes from the internet, usually from streaming services. Not to be confused with “German DL”. For German releases, usually only referred to as ‘WEB’ or “WebHD”.                                                                                            |
| WEBRip             | Also from a streaming service, but often (not always) with a lower bitrate than WEB-DL.                                                                                                                                                            |
| BluRay, Blu-Ray    | BluRay-RIP. Better quality than WEB-DL.
| Remux              | Unmodified, original BluRay rip. Only unwanted languages and menus have been removed. Best possible quality.
| MD, MIC DUBBED, MIC| Audio track was recorded in the cinema. Often poor audio quality with background noise. My recommendation: Look for a better release or wait for one :-)
| REPACK, PROPER     | These releases are revisions or corrections of a previous release. A REPACK or PROPER should be preferred to a release with the same name without this label. |

### Problems and questions

---

- My SABnzbd is not reaching its full download speed.

- **Check the causes:** Run a speed test on a site such as [Speedtest](https://speedtest.net). As a rule, you should achieve at least 80-90% of the speed you see in the speed test in SABnzbd. Note: speedtest.net shows the speed in megabits, SABnzbd in megabytes. You can convert here: https://www.gbmb.org/mbit-to-mb
If you are using a very old or slow hard drive, this could also be the bottleneck.

  - **Test download:** You can test the speed either with conventional NZBs or by using special test downloads in SABnzbd. To do this, click on the wrench in the upper right corner and start a test download (100 MB, 1 GB, or 10 GB). Please note that with block accounts, the test downloads count toward the data volume used.

  - **Adjust connections:** If the speed is not optimal, go to the server settings in SABnzbd. To do this, click on the gear icon in the top right corner, then on “Server” and then on “Show details” for your server. Under ‘Connections’ you will see a number, probably “8”. It's a matter of trial and error to find the optimal number of connections. Ewaka allows up to 50 connections, but you should never use more than 40. A good starting value could be 20. Then you can gradually increase or decrease the number of connections and test the speed each time – important: too many connections can also be a problem!

### Automation with Radarr, Sonarr, and Prowlarr

---

I will add details on how to set up Radarr, Sonarr, etc. in the next few days.
If you want to get started right away, here are a few links and some information:
1. There seems to be a very useful English tutorial here: https://www.rapidseedbox.com/blog/ultimate-guide-to-sonarr
Instead of step 5 (torrent client), add a Newznab Usenet downloader. You can find the API keys in your profile on the indexer, but as mentioned, you'll need a premium account for this.
2. For further optimization, we recommend the TraSH guides for Radarr and Sonarr: https://trash-guides.info/
3. If you prefer German DL (German+Original) releases, there is a guide by Lokilicious and me: https://trash-guides.info/Radarr/radarr-setup-quality-profiles-german-en/
Alternatively, there is also my old guide: https://github.com/PCJones/radarr-sonarr-german-dual-language

## Contact & Support
- Feel free to open an issue on GitHub if you need assistance.
- [Telegram](https://t.me/pc_jones)
- [UsenetDE Discord Server](https://discord.gg/src6zcH4rr)

## Donations
I am always happy to receive donations :D

<a href="https://www.buymeacoffee.com/pcjones" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" height="60px" width="217px" ></a>
<a href="https://coindrop.to/pcjones" target="_blank"><img src="https://coindrop.to/embed-button.png" style="border-radius: 10px; height: 57px !important;width: 229px !important;" alt="Coindrop.to me"></img></a>

For other donation options, please contact us on Discord or Telegram – thank you!
