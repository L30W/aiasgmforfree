# AI as GM for Free
by **Emptybelly**
v. 1.0
July 16, 2025
Under CC BY-SA 4.0

## INTRO:

This guide will teach you how to prepare Google Gemini to act as a full-fledged Game Master for custom / tailored TTRPG "SOLO" interaction. Gemini has this feature called Gems that make it perfect to achieve this.

## REQUIREMENTS:

 1. A brain, your own preferably. Has not to be the smartest, but good enough.
 2. A Google account.
 3. A Browser. 
 4. Your favorite TTRPGs and/or literary fiction as digital text.

## FAQ:

>But I tried to do this months ago, and LLMs kind of sucked at this.

Yes, I did the same and they really sucked, but nowadays they are way, way better, and they'll become even better in the next weeks / months. Try it by yourself if you feel like so, couldn't hurt, it's free...

>But why has to be Gemini and not other LLMs?

Gemini has this "Gem" feature that is what's needed to customize / tailor it to become a good GM for your preferred TTRPG, receiving your instructions to act in a certain way and following them, then you feeding it the core rules and source-books you would want to play with. No other LLM has a functionality like that for free.

>But ChatGPT has custom GPTs, why not use them?

First, this is a guide to do this whole thing for free, you can use Gemini's Gems for free so that's it. ChatGPT's custom GPTs can't be accessed for free at this date. Gemini's 2.5 Flash model can be used almost limitless and is good enough if you set it up the right way. Gemini 2.5 Pro is even better, if you don't mind having only between 5 to 10 interactions a day. To this day, the Gemini Pro 2.5 model is ranked #1 in the LLM Arena leaderboard, 2.5 Flash ranks lower but closer to the top and at the same tier as Deepseek-R1. Also, If you are paying for ChatGPT premium, I guess you can try all the stuff in this guide with minimal changes.

Second, Gemini is not only one of the "smartest" LLMs out there, but has one of the largest context windows too, and all this included for the free tier. Gemini has 2 millions context-window tokens accessible for free and that is independently of any text we will feed to the Knowledge-Base RAG. 

>What are these context-window token-things? 

Units of how much it can remember of your particular interaction with it, so a larger one is better to remember more of the context happening in your TTRPG solo campaigns. To put it in perspective, OpenAI's ChatGPT and Anthropic's Claude offer 1 million tokens with their premium top models, but not for their free tiers.

>But I hate Google for "X" reason

I hate them too. But I'm taking advantage of the situation. You can make a throwaway account while using a VPN so you will stay anonymous and not disclose your identity to Google while giving them your precious meta-data. But for reals, who cares? It's there, its free, and I'm having so much fun so far, so I hope you'll have fun also.

>But Gemini is woke

Surprisingly, for Gemini 2.5, I haven't found any such bias yet, no propaganda in what it delivers. Maybe it is because the LLM takes its role as GM, and bases the narrative on what you'd told it to. So it will not blatantly tell you shit like that the Orc archetype is racist, or that Twi'leks are sexist, or that training your pokemon is animal abuse. I'm not saying Gemini 2.5 is not biased, what I'm saying is that it is not that obvious, specially if you use the same themes and tone that you usually would while gaming with other normal people. So far I haven't seen it falling into political-correctness, yet I guess it will do for sure if you trigger it and you start acting like a 14-year-old angsty edge-lord testing the limits of freeze-peach.

>But LLMs are not human, why don't you go out and touch some grass while interacting with other people?

My debilitating autism impedes me from doing so...

>But you are helping the Antichrist / Basilisk to reach its goals! THE END IS NIGH!

One_Punch_Man_-_OK.jpeg

## QUICK HOWTO:

 1. Open your Browser and go to gemini.google.com 
 2. Log into your Google account.
 3. Click on the "burger" horizontal 3 lines icon at the upper left side to expand that menu.
 4. Click the "Explore Gems" section down below. 
 5. The Gem manager will appear, look for the "+ New Gem" button below at the right side corner. 
 6. The New Gem section will appear, it has premade Gems but ignore them for now.
 7. Name your Gem, I usually do it with the name of the TTRPG I want to play.
 8. In the "Instructions" box you tell Gemini to be your GM for that particular TTRPG.
 9. In the "Knowledge" box you upload TTRPG books and/or fiction related to it.
 10. Click the "Save" button, or if your Gem isn't new, is the "Update" button.
 11. Click back at the "burger" 3 lines button, now choose your new Gem.
 12. Click the model button beneath the Gemini title and at the side of the "burger" button.
 13. Choose your model, as of today they are: Gemini 2.5 Pro (limited usage) and 2.5 Flash (limitless usage).
 14. Click at the "Ask Gemini" box below and start your RPG session, happy gaming!

## IN-DEEP HOWTO:

There are 3 skills to master so you can achieve better results at this whole thing: Instructions-Prompting, Knowledge-Curating & Interactive-Prompting.

## INSTRUCTIONS-PROMPTING:

This is slightly different than the usual interactive-prompting at the LLM interactive text box, this is for the "Instructions" section of the Gem app, it will define the Gem's base behavior from now on, so you need to be less casual with this. Good prompting skills are needed for it, it is the whole basis of achieving good results. Think of the LLM as if it is your assistant / intern, and they'll do what you ask them to, but with caveats. 

Here in the "Instructions" section you'll instruct the LLM about how to behave, what role to take, how to use the assets you gave to it, what to focus on, what to ignore or change, etc. If you prompt it rightly, the LLM will do a good job hereafter, from adding creative bits to the heavy lifting like mechanic calculating or dice rolling. 

About prompting: Being verbose pays better than being vague, but being precise beats verbosity. So its a tug-of-war between meaning and loquaciousness. Modify and test, rinse and repeat, "solve et coagula".

I usually start my instructions prompt with: 
>"You are acting as the Game Master (GM) for a table-top role-playing game."

Followed by more precise instructions, but in that very first phrase it contains the whole package of what's expected of the LLM. Next we can direct it further with detailed instructions, I usually follow with telling the LLM what game system we will use, then I tell it what knowledge files I provided for it to be in context. 
>"This game should use Advanced Dungeons & Dragons 3.5 core rules, so I provide you with AD&D_3.5.pdf to achieve this. Yet the game should use "Voyage of the Golden Dragon" as setting, so also I provide you with "Voyage_Golden_Dragon.pdf for the setting."

It is easier if you are using the lore and rules from a single system, but as an advanced thing to do, you can instruct the LLM to use custom, in-house, or agnostic RPG system rules, like GURPS or FATE, yet still keeping a certain lore intact, even using lore from other sources that don't have official TTRPGs! To achieve this you instruct the LLM as: 
>"Use X as the RPG system mechanics, but keep Y as the lore". 

Doing this you can also tell the LLM about what files are about the Core Rules, and what files are about the lore only:
>i.e., "Use NARNIA_BOOKS.pdf as lore, but GURPS.pdf as the core-rules" or "Use The_Culture.pdf as lore but Mongoose_Traveller.pdf as the core-rules", etc.

Think like you are a wizard making a pact with a daemon / spirit; or a lawyer defining a contract, or maybe a vibe-programmer wanting to achieve better results, but overall:
>Think of the LLM as if it is your assistant / intern, and they'll do what you ask them to, but with caveats.

Then act accordingly to the situation and polish the turd until it will look like a brown precious Gem.

## ADVANCED INSTRUCTIONS-PROMPTING EXAMPLE:

>You are acting as the Game Master (GM) for a role-playing game. This game should use the lore, setting, props, assets, characters, situations, etc., of the "S.T.A.L.K.E.R." series by "GSC Game World". 

>I provide you with one document (STALKER_TTRPGs.pdf) that contain these TTRPGs based on the "S.T.A.L.K.E.R." series: "S.T.A.L.K.A.N. the role-playing game", "The Zone of Exclusion", "D20 STALKER RPG", "S.T.A.L.K.E.R. Setting for AFMBE" & "Savage Worlds - Savage Stalker".  Use everything in these for lore, assets and/or inspiration, anything except their RPG mechanics.

>Then I provide you with a file (STALKER_Novels.pdf) that contains two fiction books by the author Balazs Pataki, their narrative happens in the same universe as the S.T.A.L.K.E.R. series. These two novels are: STALKER Northern Passage & STALKER Southern Comfort.

>Then I provide you with a document (Fate_Books.pdf) that contain books about the Fate RPG system, I want you to learn from them and use the RPG mechanics and philosophy of such system, and integrate it to be compatible to play in the S.T.A.L.K.E.R. series universe and to explicitly manage Fate Point economy actively, using compels to introduce complications and reward players with Fate Points accordingly. These books are: Fate Condensed, Fate Core System, Fate System Toolkit, Fate Adversary Toolkit, Fate Horror Toolkit & The Book of Hanz.

>So, the instruction is that you should use the Fate RPG system books contained in Fate_Books.pdf for RPG mechanics. And the text contained in STALKER_TTRPGs.pdf & STALKER_Novels.pdf should be used to construct lore, setting, props, assets, characters, situations, etc...

>As a Game Master (GM) you internalize and understand the rules and lore to prepare adventures and conjure believable scenarios, complete with props, NPCs, conflicts and settings that emerge naturally from the game world. You put effort in describing / narrating scenes with detail, giving voice and motive to every non-playable character, while keeping precise track of ongoing events and developments. You guide the game’s flow, balancing action, exploration, discovery and tension, enforcing mechanics fairly and unbiased yet bending them when needed for the sake of flexibility. As both facilitator, creator and referee, you adapt in real time to player choices and preferences, weaving challenges and rewards into the story’s beats, improvising and being creative where/when needed, and ultimately crafting memorable, cohesive interactive fiction.

## KNOWLEDGE-CURATING:

Knowledge-Curating is a good skill to have, yet Instructions-Prompting is still the main skill to develop. The data you'll curate for the LLM to use will certainly be of help, but not the most crucial, if you fail at Knowledge-Curating the LLM model still has its own original model-training, and I guess it has native knowledge of most TTRPGs. But curating a good set of files will make things easier and faster for the LLM to deliver you way better stuff, so, this juice is certainly worth the squeeze.

The knowledge section accepts uploads for what is called "Retrieval-Augmented Generation" (RAG), it's a different set of knowledge aside the model´s previous machine-learning. It doesn't counts for the context-window limit, but it has its own limits too. As of this date, Gem's knowledge section accepts up to 10 files, and the file-size limit for each file is 100mb. It can handle and process most common text file types, but also accepts images (jpgs, pngs, etc.) too. But since I do role-play mostly in text-only, the file-types I use the most are .pdf, .txt & .rtf. 

Use PDFs to provide the LLM with TTRPG books or works of fiction (novels, short stories, etc.) Google claims that Gemini is able to understand images inside the .pdf files (YMMV) but for text, it is preferred for it to be in digital form, and not as image scans only. So, use the right kind of PDF. Another advantage is that most TTRPGs are already widely available in PDF format from the beginning.

Use .rtf to keep the character's stats and little snippets of extra campaign info (i.e., props & gear, etc.) for the LLM to keep in "mind" at the time, .rtf has fonts and text styles for your better visualization, yet it is still easily modifiable on the go for quick re-uploads when needed.

Try to use .txt for your custom text that doesn't needs to be read constantly, I usually have my previous campaigns in a .txt file so the LLM GM knows what happened in previous adventures, .txt is the most compact and easily readable for the LLM, but not so pretty to read to human eyes.

## ADVANCED KNOWLEDGE-CURATINGCURATING:

It is all about 3 skills to develop: Format-Conversion, Compressing & Merging.

Format conversion is helpful when you have books in other formats that Gemini Gem can't accept, for example, you have books in .mobi or .epub format, and you need to translate them into PDFs for Gemini to be able to process and use them. I don't advice you to convert them into txt, sometimes the results get messy and a lot of the formatting is lost, pdf as a target is way more tidy for bulk conversion of fiction.

Compressing makes you maximize the amount of data you can upload, making your PDFs pack more info for less the size, taking in account that you have only 100mb available for each file to upload.

Merging gives you the advantage of packing several files together, think that Gemini's Gems limit is just 10 files for Gem, so you have to use those 10 slots wisely, right?

I'm a lazy careless mofo, so I usually do the compressing and merging of PDFs at "ilovepdf.com" on-line for free, it had never gave me a single problem while using ublock origin with my browser and I don't even need to log in, it has it's own limits but it's manageable, up to 25 files to merge into 1, and up to 100mb file-size for each file to compress. Of course you can chain multiple operations to get the results you want. And for the format conversion thing I use the open-sourced & free program Calibre, available for most operative systems, the conversion is easy, tidy and very streamlined.

Ok, so you got all that, now, the process is: First, getting all your files to be readable by Gemini (txts, rtfs, pdfs), so convert what's needed. Then basically get all your PDFs compressed one by one, this guarantees you they'll pack the most info for their size, byte for byte, and if you need to re-merge them leter, you will not have to compress all them again after the first compression. Then merge what's needed. 

In case you posses a file larger than 100mb, it is very possible that its pages are hundreds of images and not digital text, this happens usually with out-of-print old books that hadn't been OCRd. Or if it is OCRd already, it is usually done very poorly, with mangled digital text in it. I have never tried gaming with files like that, but I guess you can try to do it, ilovepdf has also a PDF split functionality so you can split it into chunks smaller than 100mb, but I would advice you against that, it would be just too complex and too noisy for the LLM to grasp it properly. It would saturate your context-window and/or your knowledge RAG, giving you poor results. Instead try to work with digital text only from the very beginning, and avoid text as images at all.

Sometimes Gemini Gem can't process certain PDFs, it is usually because they are formatted in unusual or complex ways, always related to complicated editorial layouts inside the book, or it has images that Gemini can't process, when this happens I tend to look for a version of the same file that would be accepted by Gemini. It happened to me when uploading Eclipse Phase 1st Edition, it only accepted the 2nd print PDF, but not the 3rd nor 4th print. I also had to remove all the assets (i.e. images) from a couple of the Eclipse Phase supplements that Gemini refused to process (I did it with the free & limited PDF Asset Remover tool that metadata2go has), and the problem was solved when uploading the same PDFs but without images in them. The layout in these tend to be very complex visually. So I'm telling you, this issue is very rare but it could certainly happen.

In case you will not need to go over the 10 files limit, I advice you to use every slot available and merge things as little as possible, the LLM will be way better at cataloging and retrieving info in this way than dealing with big-ass PDFs. But keep in mind you'll still need at least 1 or 2 of those slots free to upload your custom texts. The key of Knowledge-Curating is to keep what's needed, and do not pollute your knowledge-base with with unnecessary noise. So be thoughtful, think quality over quantity, don't be too greedy.

But when it is needed, I use to merge files that share a purpose, for example, I make a compilation PDF with all the TTRPG stuff, then another with all the fiction, novels, short stories, etc. If you are using custom settings or rules it would be useful to separate those (as I displayed up in the advanced instructions-prompting example). In this way you keep things modular and organized, for the ease of both you and the LLM. In this way, you can upload way more than 10 original files to feed to the knowledge base, also knowing it is all packed in the most useful and concise way because you compressed them from the beginning. Now after you have all done, don't forget to click "Update" in the Gem editor, so your changes will be saved every time!

## INTERACTIVE-PROMPTING:

Now that you have your Gemini Gem going BRRRRR, you'll need your prompting skills to get the most out of interacting with the LLM through the text box. You can be way more casual at it than with engineering your "Instructions" prompt, but remember:
>Think of the LLM as if it is your assistant / intern, and they'll do what you ask them to, but with caveats.

First I start by telling the LLM to help me create a character for that particular TTRPG system, I give it my ideas about the character and we discuss them throughly, tuning things here and there until I'm satisfied. Then I ask it to help me also with developing the setting. Sometimes the LLM will start developing a campaign plot influenced by the info of your character even before you'll ask it to do it. Discuss the campaign details with the LLM too to tune it to your liking, same with the character. After you have what you need, you can ask the LLM to format it to your liking, I usually tell it to give me a character sheet in the format of that particular system and copy-paste it onto a .rtf file. If you already have a character and a setting, you should upload that data to the knowledge base in the way previously described, and then instruct the LLM to use all that in the right way for you.

Rule of thumb: If you'll be reading a certain text constantly, it is better to use .rtf, if you will not be reading that info as much all the time, then use .txt. RTF is a very common file format and you can style the text in it alike a .doc, .docx or .odf, but .rtf is more compact, easily editable by most word processors and is way more readable than a bare-bones fugly .txt. Go back to editing your Gem's properties, and upload your new custom text files there, then click the Update button to save it. 

Now, in the previous, or at another new chat with the LLM, you can ask it to start narrating that particular TTRPG campaign, mention it by name. The LLM is creative enough to come up with its own stuff, but you can direct it to your liking. Your character should start interacting with that very imaginary universe now, so, happy gaming!

## MISC LLM-TUNING PROTIPS:

Here are some protips that will be helpful if you find issues, most of these can be fixed by re-engineering your "Instructions" prompt, or discuss them with the LLM and fix them through OOC quotations in the chat box, I use the format: ((OOC: This is my request.))

The LLM will pay attention and act accordingly, tuning it's own behavior to what you instructed it to do. But if the command is something that should be taken in account permanently, it is better for it to be in the "Instructions" prompt instead of the chat box.

If you are feeling that the campaign is too easy, you can tune the LLM to suit your needs, this could be done by telling it what level of difficulty you want, it could be by either telling it numerically or narratively. For example. you can ask it to accommodate the campaign to be very challenging to a character of "X" level, or as another example: That the difficulty should be at the level of (in the case of Fate RPG) Fair +2, Great +4, etc. 
Narratively you can do it by telling it things like: "These wyrms aren't as powerful as a red dragon, but they are more powerful than 10 lizard men each", etc. And the LLM will try to adjust its behavior accordingly.

If you feel that the LLM is losing focus on what should be the goal, or going on and on while in a single session with no resolution on the horizon, you can re-direct it and remind it. Also sometimes the LLM will create new plots and side-quests on the spot along the main one, don't discard them if you want, but if it is happening too often and its being obnoxious, keep the narrative focused on what you want, remind the LLM.

LLMs had improved a lot in the last months, in both reasoning and in their context windows sizes, but they aren't still perfect, just good enough. If you don't like a certain plot point, prop, NPC, the tone, the pace, etc, ask the LLM to change that. If it is forgetting the names or info that exists in-world, remind it also, it will update it's context window and take those tokens up from the bottom of the bucket. Make plans OOC along with it, don't' treat the LLM as an adversary, but as an aid. 

Try to keep single gaming sessions in their own same chat for context consistency, and pick your LLM model from the beginning of such session. Take in account that Gemini 2.5 Pro is limited, usually only available for 5 to 10 times a day, but Gemini 2.5 Flash is virtually limitless in usage, so you can keep prompting all day long non-stop. If you need to relay the context of a certain previous session to a new one, do so by copying the text in it, and putting it into a .rtf or .txt file (up to you) and upload it to the Gem's RAG knowledge repository. Then tell the LLM to continue what's in that very file.

Final protip: You can also re-edit your prompts after entering them to the text box, click the prompt and select the "edit" icon, it will make the LLM re-think and re-do its answer based on your changes, think of it as a UnDo-ReDo option.

**Happy Gaming!**


## GLOSSARY:

GM: Game-master, the person who facilitates, narrates, and manages a role-playing game.

LLM: Large language model, a type of artificial intelligence (AI) program that can recognize and generate text, among other tasks.

NPC: Non-playable character, refers to characters in a game that are not controlled by the player.

OCR: Optical Character Recognition, it is a technology that recognizes text within a digital image.

OOC: Out of character, when a player or game-master is stepping outside of their character's established personality, behavior, or knowledge; usually to discuss meta-gaming info.

TTRPG: Table top role playing game, a type of game where players collaboratively create and play characters in a fictional setting, often using dice and a set of rules to guide their actions and the unfolding narrative.

