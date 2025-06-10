<p align="center">
  <img src="teleflash-logo.png" alt="TeleFlash Logo" width="300">
</p>

<p align="center">
  <strong>An event monitoring tool for journalists (functional prototype)</strong><br>
</p>

---

## Overview

Conflicts such as the war in Ukraine result in a constant feed of events. There are many sources to follow (such as military authorities, bloggers, and local eyewitnesses), and they may write in languages that few reports understand. TeleFlash is a prototype of a monitoring system for journalists that help them keep up with events, where there are numerous sources of information and language barriers. The prototype was part of action research to study what kind of digital tools would fit journalists' workflows and facilitate more varied use of sources in reporting.

TeleFlash monitors public channels covering the war in Ukrainian and Russian. It identifies messages related to Finland - a topic relevant for journalists but rarely covered elsewhere. It then uses LLMs to evaluate the relevance of events and to provide a summary of the most significant messages. The summary is delivered to a public Slack channel, to faciliate discussion between journalists.

The work was done as part of the [Re-imagining Finnish conflict reporting
](https://researchportal.helsinki.fi/en/projects/re-imagining-finnish-conflict-reporting) project at the University of Helsinki.

## Example of output


---
                      🇫🇮 Finland-Related Messages Summary                       
---

Analysis Period: 2024-04-27 to 2024-04-28


🔍 Analysis of Messages about Finland and Generated Summary:
---
Overview:

In the last day, several newsworthy developments related to Finland have been reported, including military exercises in the Gulf of Finland, Finland's diplomatic relations with Russia, and aviation issues affecting Finnish flights.

Key Topics:

Military Exercises in the Gulf of Finland:
According to (severnygorod-291902), special forces exercises of the Russian National Guard (Rosgvardia) took place in the waters of the Gulf of Finland. The exercises involved SOBR fighters being alerted, transported by Mi-8 helicopters, and conducting diving operations in the water with mountaineering equipment.

Diplomatic Relations with Russia:
As reported by (tass_agency-317048), during a briefing, Maria Zakharova highlighted Russia's intention to transfer a memorandum to Kyiv for the settlement of the Ukrainian conflict once it is developed. Zakharova also mentioned Russia's recognition of Minsk's significant contribution to the prisoner exchange with Ukraine and criticized Western influence on Helsinki, claiming it undermines Finland's security.

Aviation Issues Affecting Finnish Flights:
Finnair decided to suspend daily flights to the Estonian city of Tartu due to GPS system disruptions, as stated in (octgnews-49737). The airline plans to develop landing methods at the Tartu airport to safely operate flights without GPS signals. This decision comes after an incident where a Finnair plane returning to Helsinki from Estonia was unable to land in Tartu due to the GPS system requirement specific to that airport, according to (octgnews-49686).

Counter-Drone Measures in Finland:
Reported by (octgnews-49688), Finnish police and military have received anti-drone rifles to combat unauthorized drones flying in restricted areas. These devices are equipped with jamming systems to intercept and disrupt drone control, forcing them to return or land. The Air Force Commander, Juha-Pekka Keränen, mentioned that several UAVs have already been brought down using these measures, emphasizing their effectiveness against civilian drones.

These developments underscore the various aspects of Finland's engagements in military exercises, aviation operations, diplomatic relations with Russia, and efforts to enhance security through modern technology and defense measures.

---

📊 Basic Metrics:
• Total Messages Analyzed (related to Finland): 73
• Total Views: 81,683
• Total Forwards: 79

📈 Average Metrics:
• Avg Views/Post: 11669.0 (how many views each post related to Finland gets on average)
• Avg Forwards/Post: 11.3 (how many times each post related to Finland is shared on average)
• Base Engagement: 0.1% (how many viewers share the content about Finland)

🔄 Advanced Engagement:
• Views/Forwards Ratio: 1034.0 (how many people view before someone shares)
• Virality Score: 1.1% (how likely content is to spread)
• Unique Channels: 4 (number of different channels posting about Finland)

📊 Distribution Patterns:
• Posts/Day: 13.3 (average number of posts each day)
• Peak Daily Posts: 21 (highest number of posts in one day)
• Channel Activity Ratio: 1.8 (average posts about Finland per channel)

---

## ⚙️ Installation

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd teleflash
   ```

2. **Set Up Environment**:
   Create a `.env` file in the project root with the following variables:
   ```
   API_ID=your_api_id
   API_HASH=your_api_hash
   PHONE=your_phone_number
   SESSION_FILE=session.session
   DB_USER=your_db_user
   DB_PASSWORD=your_db_password
   DB_HOST=your_db_host
   DB_NAME=your_db_name
   OPENAI_API_KEY=your_openai_api_key
   SLACK_BOT_TOKEN=your_slack_bot_token
   SLACK_CHANNEL_ID=your_slack_channel_id
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

---

## 🚀 Usage

### Scripts
- **`channel_content.py`**: Scrapes Telegram channels and stores posts in the database.
- **`teleflash.py`**: Filters Finland-related posts, summarizes them, and posts to Slack.
- **`scheduler.py`**: Runs both scripts daily at 06:00.

### Manual Execution
Run the scripts individually:
```bash
python channel_content.py
python teleflash.py
```

### Automatic Execution
Start the scheduler for automated daily runs:
```bash
python scheduler.py
```
---

## 📢 Current List of Channels

The scraper currently monitors **the following Telegram channels** (usernames):

<details>
<summary>Click to expand</summary>

`severnygorod`, `agapov_fi`, `karaulny`, `rusbrief`, `octgnews`, `tass_agency`, `baltnews`, `fontankaspb`, `dprunews`, `sp_1703`, `glavmedia`, `houseofcardseurope`, `good78news`, `rian_ru`, `belta_telegramm`, `radiogovoritmsk`, `bbbreaking`, `paperpaper_ru`, `nevnov`, `swodki`, `vzglyad_ru`, `parstodayrussian`, `ukraina_ru`, `solovievlive`, `rossiyaneevropa`, `online47news`, `riafan`, `radiomirby`, `dirtytatarstan`, `rgrunews`, `inosmichannel`, `sputnikby`, `rbc_news`, `ssigny`, `boyart777`, `lentadnya`, `radiosvoboda`, `kommersant`, `topspb_tv`, `allnews47`, `rt_russian`, `absatzmedia`, `match_tv`, `truekpru`, `bbcrussian`, `houseofcardsrussia`, `OdessaRussi`, `Novoeizdanie`, `rus_demiurge`, `stranaua`, `rbc_brief`, `aifonline`, `ostashkonews`, `dimsmirnov175`, `ateobreaking`, `infantmilitario`, `UAnotRU`, `smotri_media`, `thehandofthekremlin`, `leningrad_guide`, `izvestia`, `meduzalive`, `highlylikely20`, `rentv_news`, `znua_live`, `atn_btrc`, `vestiru24`, `chvkmedia`, `espresotb`, `kshulika`, `orientsouthrus`, `dwglavnoe`, `ZOVcrimea`, `Belarus_VPO`, `readovkanews`, `ranarod`, `gazetaru`, `nexta_live`, `ntvnews`, `uniannet`, `lady_north`, `fuckyouthatswhy`, `nstarikovru`, `new_militarycolumnist`, `mk_ru`, `lab365`, `go338`, `postovo`, `asphaltt`, `politkraina`, `rlz_the_kraken`, `ru2ch`, `bfmnews`, `russtrat`, `tv360`, `radio_sputnik`, `minut30`, `pluanews`, `rtvinews`, `interfaxonline`, `istorijaoruzijaz`, `currenttime`, `sputniklive`, `newsgrpua`, `srochnow`, `ukrpravda_news`, `first_political`, `oldlentach`, `RUSanctions`, `Pravda_Gerashchenko`, `warhistoryalconafter`, `ivan_utenkov13`, `TCH_channel`, `the_moscow_post`, `UkraineNow`, `openukraine`, `ukr_shvydko`, `lentachold`, `huyovy_kharkiv`, `kontext_channel`, `russica2`, `tvrain`, `operativnozsu`, `rus_now_news`, `voynareal`, `lachentyt`, `russianonwars`, `dmytrogordon_official`, `banksta`, `TolkoPoDely`, `rybar`, `rhymestg`, `ragnarockkyiv`, `ukraina24tv`, `bankrollo`, `truexanewsua`, `sheyhtamir1974`, `aleksandrsemchenko`, `tsaplienko`, `varlamov_news`, `DavydovIn`, `boris_rozhin`, `RVvoenkor`, `redacted6`, `zerkalo_io`, `voenacher`, `Mikle1On`, `UaOnlii`, `vchkogpu`, `kaktovottak`, `novosti_efir`, `shot_shot`, `insiderUKR`, `slavaded1337`, `bloodysx`, `breakingmash`, `readovkaru`, `ostorozhno_novosti`, `okoo_ukr`, `Cbpub`, `warfakes`, `montyan2`, `moscowmap`, `asupersharij`, `nevzorovtv`, `V_Zelenskiy_official`, `yurasumy`

</details>

---

### ✏️ How to Change This List

1. **Open `channel_content.py` and `teleflash.py`:**
   - The channel list is defined as a Python list named `channels` or `channels_list` near the top of each file.

2. **Edit the List:**  
   - Add or remove channel usernames as needed – just like editing a Python array.
   - Example:
     ```
     channels = [
         'severnygorod', 'agapov_fi', 'karaulny',  # etc.
         # 'channel_to_remove',
         'some_new_channel'
     ]
     ```

3. **Save and Restart:**  
   - Save your changes.
   - The next time you run the scripts (or the daily scheduler runs), your updated channel list will be used!

---

## 📁 File Overview

| File                  | Description                              |
|-----------------------|------------------------------------------|
| `init.py`             | Telethon connection and helper functions |
| `channel_content.py`  | Logic for scraping and saving to DB      |
| `teleflash.py`        | Filtering, summarizing, and Slack posting|
| `scheduler.py`        | Daily automation script                  |
| `models.py`           | SQLAlchemy ORM models                    |
| `requirements.txt`    | Project dependencies                     |

---

## 🤝 Funding

This project is proudly funded by **Media-alan tutkimussäätiö**.

---

## 👥 Our Team

| Name                  | Contact                                  |
|-----------------------|------------------------------------------|
| **Vasileios Maltezos** | [vasileios.maltezos@helsinki.fi](mailto:vasileios.maltezos@helsinki.fi) |
| **Roman Kyrychenko**   | [GitHub account](https://github.com/RomanKyrychenko)     |
| **Aleksi Knuutila**    | [GitHub account](https://github.com/AleksiKnuutila)       |
