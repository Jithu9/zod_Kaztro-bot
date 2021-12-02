# zod_Kaztro-bot
WhatsApp bot
📢 WhatsAsena Version 1.2 Is Available Now!
…
* Fix Lydia 🛠️

* Carbon API Changed ⬆️

* Added "Easy Changeable Modul's Texts" Plugin 🥳

Just convenience, with this feature we don't need *.setvar*  to change modul's texts.

* Lang Update TR ⬆️

* Fix

* Added Block and Unblock Config 🥳

* Added Env for Block and Unblock Messages ⬆️

* Update README.md

* Added İnformation After Unsuccessful Update 🥳

* Added Hide Tagall 🥳

Now you can tag group members without tag buttons.
You must use .tagall text format to use hide tagall.

* İmproved Tagall 🥳

* Fixed Split Error ⚒️

* Improved Plugins 🥳

* Imoroved Asena Plugin 🥳

* Improved Xmedia 🥳

* Fixed Add Plugin and Improved Other Things 🥳

* Removed Lydia ⚠️

* Improved Carbon 🥳

* Improved Converter 🥳

* Improved DeepAI 🥳

* Improved Meme 🥳

* Improved Nekobin 🥳

* Improved OCR 🥳

* Improved JID Module 🥳

* Improved RemoveBG 🥳

* Improved Scrapers 🥳

* Improved Screenshot Plugin 🥳

* Update _plugin.js

* Improved Social Scraper 🥳

* Improved Someone Say 🥳

* Improved Stickers 🥳

* Improved System Stats and Added Variables for Alıve Message 🥳

Now, you can set varibale in alive message. 
{pp} = It was enough to use it 1 time. It gets your profile pic.
{version} = It gets bot's version
{info} = It gets your status

* Improved Tagall - Added Scan and TagAdmin Plugin 🥳

* Added Whois Plugin 🥳

* Added Log Plugin 🥳

* Improved Tblend 🥳

* Improved TTP 🥳

* Improved Unvoice 🥳

* Improved Voicy 🥳

* Improved Wallpaper 🥳

* Improved Weather 🥳

* Improved Short Module 🥳

* Ping Module Fixed ⚒️

* Log Improved 🥳

* Fix Log Plugin 🛠️

* Added Config for Add Message 🥳

* Baileys Version Updated ⬆️

* New Bailyes Version Integrated Into the WhatsAsena ⬆️

Thanks @lyfe00011 for codded this.

* Added Customizable Add Massage 🥳

* Language Update TR ⬆️

* Added AnimAI and FaceAI Plugins 🥳

* Update TR.json

* Security Update ⬆️

* Merge Main Commit

* Added Helper for Wrong Plugin Names 🥳

* Mini UI Fix 🛠️

* Added Customizable Block & Unblock Messages Inside Commands 🥳

* Merge Main Commit

* Merge Main Commit

* Removed Tiktok Downloader [ API Problem ]

* Fixed Installing Wrong Plugins 🛠️

* İnstagram Scraper Renewed 🥳

Thanks @lyfe00011 for codded this unique module.

* Fix 🛠️

* Added Plugin Channel Config ⬆️

* Added {plugin} variable for Plugin Channel and Overall Improvements ⬆️

* Language Update AZ ⬆️

* Insta Module UI Fix 🛠️

* Fix Again

* Language Update TR ⬆️

* Mini Fix [AZ]

* Fix AZ Language Json 🛠️

* Lang Update EN

* Lang Update ES ⬆️

* Lang Update HI ⬆️

* Added 1 Second Delay for Every Filter Message [ For Spam Trigger  ]

* Added AI Command Scanner [Renewed] 🥳

* Add files via upload

* Update updown.js

* Codefactor Issues

* Fix

* Of course I still love you [ Fix Again ]

* Codefactor Issues

* Codefactor Issues

* Improved AI Scanner ⬆️

* Improved Carbon & Added Background Color 🥳

* Fix

* Update Whois ⬆️

* Update Language TR ⬆️

* Language Update AZ ⬆️

* Language Update EN ⬆️

* Language Update ES ⬆️

* Language Update HI ⬆️

* Language Update ID ⬆️

* Update EN.json

* Update ES.json

* Update HI.json

* Lang Update ML ⬆️

* Fix AZ Language

* Fix EN Language

* Fix ES Language

* Fix HI Language

* Fix ID Language

* Fix TR Language

* Fix Scan 🛠️

* Lyida SQL Removed

* Update similarity.js

* Update updown.js

* Language Update PT

* Version Changed 1.2

* Update bot.js

* Update bot.js

Co-authored-by: lyfe00011 <76509367+lyfe00011@users.noreply.github.com>
Co-authored-by: Thiccy <atpenerji1@gmail.com>
 3 contributors
37 lines (30 sloc)  995 Bytes
/* WhatsAsena Duplicated - Artificial Intelligence Similarity
Codded by lyfee
function similarity(first, second) {
	first = first.replace(/\s+/g, '')
	second = second.replace(/\s+/g, '')
	if (first === second) return 1; // identical or empty
	if (first.length < 2 || second.length < 2) return 0; // if either is a 0-letter or 1-letter string
	let firstBigrams = new Map();
	for (let i = 0; i < first.length - 1; i++) {
		const bigram = first.substring(i, i + 1);
		const count = firstBigrams.has(bigram)
			? firstBigrams.get(bigram) + 1
			: 1;
		firstBigrams.set(bigram, count);
	}
	let intersectionSize = 0;
	for (let i = 0; i < second.length - 1; i++) {
		const bigram = second.substring(i, i + 1);
		const count = firstBigrams.has(bigram)
			? firstBigrams.get(bigram)
			: 0;
		if (count > 0) {
			firstBigrams.set(bigram, count - 1);
			intersectionSize++;
		}
	}
	return (2.0 * intersectionSize) / (first.length + second.length - 2);
}
module.exports = {similarity:similarity}
