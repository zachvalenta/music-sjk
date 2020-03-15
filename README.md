# sw around music library

* _model_: relational
* _interface_: ?

* current headers to store: albums, live, songs, parts
> also store output of file watcher?

* _artists_: The Band, Cody Chesnutt, D'Angelo, Stevie Wonder, Nas, Jay-Z, Andre, TVotR
* _code music_: ambient, drone, idm
* _cover art_: Lost in Translation alternate, Miles Davis someday my prince will come Ohio Players all Slint spiderland Diana Ross first album
* _erosion of ownership_: subscription, DRM, end-user license agreements https://www.eff.org/deeplinks/2017/05/book-review-end-ownership%0A https://news.ycombinator.com/item?id=15862494
* _high points_: Stevie Wonder for the 70s, Wu Tang in 1995, TVotR in the 2000s
* _intros_: Beach Boys wouldn't it be nice, Diana Ross i'm coming out, Fucked Up broken head, Mount Kimbie home recording, Ghostface back like that, Theme from S Express has the best intro of all time
* _Philly_: Barbara Mason, Coltrane, Philly Joe Jones, Jaco Pastorius, McCoy Tyner, Roots, The Trammps, War on Drugs, Delfonics
* _playlist_: baby it's you, baby it's me
* _titles - albums_: Ramones 'Too Tough to Die' https://en.wikipedia.org/wiki/The_Powers_That_B#Niggas_on_the_Moon https://en.wikipedia.org/wiki/Turn_It_Up_Faggot https://en.wikipedia.org/wiki/I_Don%27t_Like_Shit,_I_Don%27t_Go_Outside https://en.wikipedia.org/wiki/Who_Is_This_Bitch,_Anyway%3F
* _titles - songs_: I'm Leaving You Because I Don't Love You
* _underappreciated geniuses_: Cody Chesnutt, Jens Lekman
* _upset_: Illmatic intro, Legend, Many Men, Walk, U Guessed It, Mantra, A Lot, Return of the G, Praying for Help, Nowhere2Go, Alright, Yah, Love, Fear, Hail Mary, Heaven

__lifetime__

* _guides_: parents (the Who) DVDs (Incubus, Led Zeppelin) Paste Magazine, Penn State library and Pitchfork and Jack, Hella Tight and Wikipedia, Christgau and Wikipedia, Swafford and Neely

* high school: 
* Penn State: only built 4 cuban linx, london calling
* Dalian: 
* Nanjing: 
* Philadelphia: 
* Delaware: 
* NYC: 
* London: a lot
* NYC: 

__moments__

* 2003: listening to 'Rich' going into the Lincoln Tunnel
* 2003: turn on 'De-Loused in the Comatorium' in my room, sit down
* 2006: TV on the Radio at Starlight Ballroom, Radiohead at Bonnaroo, Clipse in Pittsburgh
* 2010: Carsick Cars in Beijing
* 2016: Xiu Xiu does Laura and Leland
* 2017: Caravan in my apartment
* 2019: Bruce and Dancing in the Dark at Astor Bar

## tooling

* download from Soundcloud and Bandcamp https://github.com/Miserlou/SoundScrape
* _metadata_: https://bitheap.org/dnuos/ http://oidua.suxbad.com/ https://www.theverge.com/2019/5/29/18531476/music-industry-song-royalties-metadata-credit-problems http://richardmavis.info/tagging-files
* _NAS (network attached storage)_: aka 'home media server'; options (Plex, cmus remote) https://www.youtube.com/results?search_query=cmus+remote&page=&utm_source=opensearch https://www.youtube.com/watch?v=UJw9YU_SBzo https://blog.dave.tf/post/building-nas-1/ https://www.youtube.com/results?search_query=build+a+nas https://www.youtube.com/results?search_query=buy+a+nas https://kevq.uk/my-home-server-2-months-on/
> all this work just to stream music doesn't make sense, just keep rolling w/ backups and your $60 thumb drive
* _tagging_: http://beets.io/ + Meta ('Benjamin Jaeger' 🗄 `Applications/Meta`) https://github.com/beetbox/mediafile https://musicbrainz.org/

__Looper__

* _inspiration_: https://wiki.python.org/moin/PythonInMusic https://www.youtube.com/watch?v=1fr_5v6nc-s
* things in this space: https://www.reddit.com/r/Guitar/comments/3v4tql/how_to_slow_down_music_in_order_to_play_along/ https://music.tutsplus.com/tutorials/10-apps-for-slowing-down-solos--audio-7516 Anytune https://www.youtube.com/results?search_query=anytune&page=&utm_source=opensearch Transcribe https://www.seventhstring.com/xscribe/screenshots.html https://wiki.python.org/moin/PythonInMusic
* _features_: loop section (like Steezy) add metronome, slow down (you don't need to warp if Youtube doesn't) https://stackoverflow.com/q/9953219/6813490

__file watch__

poc
```sh
alias mlib="cd /Volumes/MUSIC-LIB && t > ~/Desktop/music-lib-$(date +"%Y%m%d").log"
```

* _sink_: https://github.com/watchexec/watchexec https://facebook.github.io/watchman/ https://github.com/emcrisostomo/fswatch https://vsoch.github.io/watchme/getting-started/ https://github.com/cespare/reflex https://github.com/cortesi/modd  --> `mlib` `os.walk()` https://unix.stackexchange.com/questions/90115/convert-output-of-tree-command-to-json-format/ regex to strip and kebab https://github.com/30-seconds/30-seconds-of-python#kebab https://www.robertchristgau.com/get_gl.php?g=A%2B store library song info as db

__editing__

https://github.com/jiaaro/pydub https://realpython.com/playing-and-recording-sound-python/

```python
from pydub import AudioSegment
song = AudioSegment.from_mp3("april-in-paris.mp3")
first_10_seconds = song[:10000]
repeated = first_10_seconds * 2
repeated.export("mashup.mp3", format="mp3")
```

## cmus

* _config_: `~/.config/cmus`
* _docs_: https://github.com/cmus/cmus/blob/master/Doc/cmus-tutorial.txt bad and won't get better because project not maintained https://github.com/cmus/cmus/issues/856
> There are more commands and features not covered here like loading and saving playlists, controlling cmus remotely with `cmus-remote`, etc.
* _features_: playlist from plain text

* _mark_: for bulk operations; `space`

nav

* _up/down_: Vim
* _top/bottom_: Vim
* _enter/leave_: `RETURN / DELETE`
* _search_: Vim

play

* _play/pause_: `c`
* _restart_: `x`
* _skip - back/forward_: `z/b`
* _skip - seconds - back/forward_: `:seek +/-<num>` 

views

* _library - clear_: `:clear`
* _playlist - add_: `y`
* _queue - prepend_: `E`
* _queue - append_: `e`
* _queue - rm_: `D`
* _queue - rm - all_: `:clear -q`
* _queue - reorder_: `p (down) P (up)`
* _update_: `u`

config

* _add music_: `a` in browser view on dir to add https://github.com/cmus/cmus/issues/233#issuecomment-399426415
* _continue_: `C`
* _shuffle_: `s`
* _play from_: `m`
* _toggle play from library or playlist_: `M`
* _display - time remaining in song_: settings - 'show_remaining_time'
* _display - hidden files_: `i`

## albums

__top 10__

* _Band_: Northern Lights Southern Cross
* _Brian Eno_: Another Green World
* _Clipse_: Hell Hath No Fury
* _Cody Chesnutt_: Headphone Masterpiece
* _D’Angelo_: Black Messiah
* _Dilla_: Donuts
* _Ellington_: Money Jungle
* _KLF_: Chill Out
* _Miles Davis_: Sketches of Spain
* _Sly Stone_: Riot Going On
* _Stones_: Exile on Main Street
* _Van Morrison_: Astral Weeks

__dance__

* _Derrick May_: Live in Sciabecco
* _DJ Richard_: Grind
* _The Field_: Looping State of Mind, Cupid's Head
* _Omar S_: The Best
* _The Field_: Looping State of Mind

__jazz__

* _Chet Baker_: Chet Baker Sings
* _Coltrane_: Blue Train, Love Supreme
* _Ellington_: Money Jungle
* _Horace Silver_: Jazz Messengers, Songs for My Father
* _Kamasi_: The Epic
* _Mingus_: Ah Um
* _Miles Davis_: Sketches of Spain, Bitches Brew

__rock__

* _Beatles_: Please Please Me, White Album
* _Bob Dylan_: Highway 61
* _Band_: Music from Big Pink, Basement Tapes, Northern Lights Southern Cross
* _Broken Social Scene_: first album
* _Dennis Wilson_: Pacific Ocean Blue
* _Jimi Hendrix_: Are You Experienced?
* _My Morning Jacket_: Tennessee Fire, Z
* _Neil Young_: After the Goldrush, Tonight's the Night
* _Pure X_: Pleasure
* _Radiohead_: In Rainbows
* _Ramones_: self-titled
* _Rolling Stones_: Sticky Fingers, Exile on Main Street
* _Stooges_: Stooges, Funhouse
* _TV on the Radio_: Desperate Youth Bloodthirsty Babes, Cookie Mountain
* _Wire_: Pink Flag
* _Yeah Yeah Yeah_: Fever to Tell

__r-n-b__

* _Anita Baker_: Rapture
* _D’Angelo_: Voodoo, Black Messiah
* _James Brown_: Live at the Apollo
* _Steve Wonder_: Music of My Mind, Talking Book
* _Sly Stone_: There’s a Riot Goin’ On

__rap__

* _Clipse_: Hell Hath No Fury
* _Game_: Documentary 2
* _Kendrick_: Damn
* _Outkast_: ATLiens, Aquemini, Stankonia
* _Vince_: Stolen Youth
* _Wu_: Only Built 4 Cuban Linx

__za__

* _Arthur Russell_: World of Arthur Russell, World of Echo
* _Babatunde Olatunji_: Drums of Passions
* _Brian Eno_: Another Green World
* _Cody Chesnutt_: Headphone Masterpiece
* _Dilla_: Donuts
* _KLF_: Chill Out
* _Portishead_: Dummy
* _Talk Talk_: Spirit of Eden, Laughing Stock
* _Van Morrison_: Astral Weeks
* _xx_: xx

## live

__irl__

* Car Sick Cars
* Pairs
* TV on the Radio

__TV__

* At the Drive-In: Letterman
* D'Angelo https://www.youtube.com/watch?v=3woHfDKTjqU
* Josh Ritter on Jools Holland
* Mary J https://www.youtube.com/watch?v=gIH-Yptxf54
* Sly Stone: Higher

__albums__

* _Jill Scott_: 08.26
* _Rolling Stones_: Get Yer Yayas Out
* _Wilco_: Kicking Television

---

* Andrew Bird
* Beck
* Black Crowes and Jimmy Page
* Bob Dylan
* Boris
* Boyz2Men
* Bruno Mars
* Carsick Cars
* Clipse
* Coldplay
* Cold War Kids
* Conor Oberst
* Courtney Barnett / Kurt Vile
* Dave Matthews Band
* Delorean
* Derek Trucks
* Eric Clapton
* Farm Aid: Willie Nelson, Neil Young
* Fiery Furnaces
* The Format
* Glass Candy
* Guster
* Hold Steady
* Inc.
* Jessie Ware
* Jill Scott, Boyz2Men
* Julianna Barwick
* Kurt Vile and Courtney Barnett
* Little Feat
* Mars Volta (2x)
* My Morning Jacket
* No Age
* Noisettes
* Pairs
* Pawnshop Roses
* Pepper’s Ghost
* Radiohead
* Red Hot Chili Peppers
* Robert Randolph
* Rolling Stones (2x)
* Roots
* Sigur Ros
* Sufjan Stevens
* TV on the Radio (2x)
* Virginia Coalition
* Weezer
* the Who
* Wiz Khalifa
* Wolf Parade
* Xiu Xiu
* Yeah Yeah Yeahs
* YLT: Brian Chase on drums, McNew smiling at riffs he likes, comedian opener

## songs

__top 10__

* _Aly Us_: Follow Me
* _DJ Rashad_: Let It Go
* _Donny Hathaway_: You've Got a Friend
* _Ellington_: In a Sentimental Mood
* _Johnny Clarke_: Love Me Forever
* _KC and the Sunshine Band_: Keep It Coming Love
* _My Bloody Valentine_: Sometimes
* _Ronettes_: Do I Love You
* _Stones_: Can't You Hear Me Knocking
* _Stevie_: Have a Talk with God
* _Van Morrison_: Sweet Thing

__dance__

* _Aly Us_: Follow Me
* _Alex Danilov_: Deep S
* _DJ MC_: Y Fall
* _DJ Rashad_: Let It Go, Leavin, Let U No, I'm Too Hi
* _Donna Summer_: We Can Make It, Love to Love You
* _Jlin_: Erotic Heat
* _KC and the Sunshine Band_: Keep It Coming Love
* _Kelela_: Bank Head
* _The Knife_: Heartbeats
* _Larry Heard_: Never No More
* _Lectrovluv_: If We Try
* _Machine Drum_: Fantastix
* _Matthew Herbert_: It's Only
* _Mia Hesterly_: Spark
* _Omar S_: On Your Way
* _S'Express_: Theme from S'Express
* _Sound Mechanix_: I Can't Forget
* _Tencity_: How Love Is
* _Young Galaxy_: Pretty Boy
* _Young Smoke_: Space Muzik Pt. 3

__jazz__

* _Coltrane_: Blue Train, Naima, In a Sentimental Mood, Moment's Notice
* _Derrick Hodge_: For Generations
* _Ellington_: Fleurette Africaine
* _Miles_: It Never Entered My Mind, My Funny Valentine, Someday My Prince Will Come
* _Mingus_: Open Letter to Duke
* _Horace Silver_: Calcutta Cutie

__pop__

* _Baby Shakes_: Love Machine
* _Camera Obscura_: French Navy
* _Kid Wave_: Sway
* _Orioles_: Too Soon to Know
* _Ronettes_: Do I Love You

__rap__

* _50_: How to Rob, Many Men, Ayo
* _ASAP_: Trilla, Suddenly
* _Big Boi_: Ghetto Musick, Church, Tomb of the Boom, In the A
* _Big Krit_: Big Bank, Higher Calling
* _Big L_: Danger Zone
* _Camron_: Forever, Take Em to Church, I Hate My Job
* _Chance_: Everybody's Somebody's Everything, I Am Very Very Lonely, Somewhere Nowhere USA, Ultralight Beam, How Great  
* _Danny Brown_: The Return, Lonely, Clean Up, Kush Coma, Really Doe
* _Drake_: Legend, Sandra's Rose
* _Dram_: Money
* _Earl_: Mantra, Grief
* _Fugees_: Zealots, Family Business
* _Jay_: PSA, U Don't Know
* _Juicy J_: Bandz
* _Ka_: Peace Ahki
* _Kanye_: Devil in a Red Dress, No More Parties in LA
* _Kendrick_: i, Fear
* _Mike Jones_: Still Tippin
* _Nas_: NY State of Mind + pt. 2, Get Down, Nasty
* _Outkast_: Hootie Hoo, Elevators, Wailin, Return of the G, West Savannah, Art of Story Telling, Spottie, Snappin & Trappin, BoB, Intl Players Anthem, Morris Brown
* _Raekwon_: Have Mercy
* _Tupac_: Hail Mary
* _Vince_: Heaven, Blue Suede
* _Wayne_: Ice Cream, La La, Mad, A Milli
* _Wu_: Ice Water

__r-n-b__

* _Alexandria_: Problem
* _Anita Baker_: You Bring Me Joy
* _Barbara Mason_: Yes I'm Ready, Another Man
* _Betty Davis_: Big Freak
* _Brandy_: As Long As You're Here
* _CeeLo_: No One's Gonna Love You
* _Charles Wright_: Do Your Thing, Express Yourself
* _Cody Chesnutt_: With Me in Mind, Can We Teach Each Other
* _D'Angelo_: Back to the Future
* _Diana Ross_: I'm Coming Out
* _Donny Hathaway_: You've Got a Friend
* _Gap Band_: Yearning for Your Love
* _Harold Melvin_: I Miss You
* _Herbie Hancock_: Thought It Was You
* _Hot Chip_: Bad Luck
* _Isacc Hayes_: Walk on By
* _James Brown_: The Payback
* _Jessie Ware_: Keep on Lying to Me, Kind of Sometimes Maybe
* _Jill Scott_: One, Prepare
* _Kehlani_: CRZY, The Way
* Like a Virgin demo
* _Mario_: Just a Friend
* _Massive Attack_: Shelter
* _Maxwell_: Pretty Wings
* _Michael_: It's the Falling in Love
* _Neyo_: Religious
* _Nick Lowe_: 36 Inches
* _Ohio Players_: Honey
* _Prince_: Head
* _Raphael Saadiq_: Don't Fall in Love
* _Sade_: When Am I Going to Make a Living
* _Shirelles_: Baby It's You
* _Stevie_: Sugar, Sunshine in Their Eyes, I Love Every Little Thing, Keep on Running, I Believe, Rocket Love
* _Sly Stone_: Time
* _SZA_: Child's Play
* _Teddy Pendergrass_: It Don't Hurt Now
* _Teyana Taylor_: Rose in Harlem
* _Timmy Thomas_: Why Can't We Live Together
* _Tina Turner_: - Keep On Pushing
* _Trammps_: Hold Back the Night

__rock__

* _Angel Olsen_: Heart-Shaped Face
* _Antlers_: Rolled Together, Hotel, Revisted
* _Beach Boys_: Wouldn't It Be Nice
* _Beatles_: I'm Looking Through You, In My Life, I Want You, Helter Skelter, Don't Let Me Down
* _Billy Riley_: Red Hot
* _Black Sabbath_: War Pigs
* _Blondie_: Heart of Glass, Sunday Girl
* _Bowie_: Heroes
* _Broken Social Scene_: Lover's Spit
* _Bully_: Either Way
* _Buzzcocks_: I Believe
* _Clash_: Police on My Back
* _Cymbals Eat Guitars_: Warning
* _Death Grips_: I Break Mirrors on My Face in the United States
* _David Vandervelde_: Nothin No
* _Eleanor Friedberger_: I'll Never Be Happy Again
* _Exploding Hearts_: I'm a Pretender
* _Grateful Dead_: Morning Dew
* _Green Day_: Having a Blast
* _Haim_: Honey and I
* _Hendrix_: Spanish Castle Magic, If 6 Was 9
* _Joy Division_: Ceremony
* _King Khan_: Welfare Bread
* _Led Zeppelin_: Since I've Been Loving You, Misty Mountain Hop, Hey Hey What Can I Do, Ten Years Gone, In the Light, Whole Lotta Love
* _Lennon_: God
* _Litle Big League_: Sucker
* _New Order_: Truth, Age of Consent
* _Nick Lowe_: Rollers Show
* _Nirvana_: In Bloom, Sliver
* _No Doubt_: Sixteen
* _Peter Bjorn and John_: Objects of My Affection
* _Phoenix_: Courtesy Laughs, Second to None
* _Pure X_: Voices
* _Radiohead_: House of Cards
* _Red Hot Chili Peppers_: Made You Feel Better
* _REM_: Radio-Free Europe
* _Replacements_: Waitress in the Sky, Swinging Party
* _Rolling Stones_: Let's Spend the Night Together, No Expectations, Sticky Fingers (Can't You Hear Me Knocking, Dead Flowers, Moonlight Mile), I Just Want to See His Face, Star Star, Til the Next Goodbye
* _Sleater Kinney_: One More Hour
* _Sonics_: Psycho
* _Talking Heads_: Heaven
* _Tame Impala_: Nangs
* _T-Rex_: Metal Guru
* _TV on the Radio_: Playhouses
* _Undertones_: Teenage Kicks
* _Yo La Tengo_: Blue Line Swinger, You Can Have It All
* _Wilco_: California Stars
* _Wu Lyf_: 14 Crowns

__za__

* _Arthur Russell_: Wild Combination, Keeping Up
* _Babatunde Olatunji_: Gin Go Lo Ba
* _Billy Boy Arnold_: Wish You Would
* _Boris_: Flood 2
* _Brian Eno_: Swastika Girls
* _Clams Casino_: Natural
* _Dilla_: Stop
* _Dylan_: Cocaine Blues
* _Eddie Santiago_: Lluvia
* _Eric Chenaux_: Love Don't Change
* _Fela_: Woman
* _Garth Brooks_: Friends in Low Places
* _My Bloody Valentine_: Glider, Sugar, Sometimes
* _Majical Cloudz_: Impersonator
* _Roisin Murphy_: Exploitation
* _Patsy Cline_: Strange, She's Got You
* _Red Hot Chili Peppers_: Porcelain
* _Talk Talk_: New Grass
* _Van Morrison_: Caravan, Sweet Thing
* _xx_: VCR, Shelter

__folk__

* _Arthur Russell_: Goodbye Old Paint, I Won't Be Around Anymore
* _Bill Callahan_: Riding for the Feeling, One Fine Morning
* _Kelis_: Bless the Telephone
* _Neil Young_: Cripple Creek Ferry
* _Nick Drake_: Pink Moon
* Indian War Whoop

__reggae__

* _Brian and Tony Gold_: Sweet Baby
* _Clash_: Equaliser
* _Dennis Brown_: Wolves and Leopards
* _Johnny Clarke_: Love Me Forever
* _Junior Murvin_: Police and Thieves
* _Scientist_: Miss Know It All
* _Shabba Ranks_: Peenie Peenie
* _Wayne Smith_: Under Me Sleng Teng

__love__

* _Angel Olsen_: Heart Shaped Face
* _CeeLo_: No One's Gonna Love You
* _Girls_: Heartbreaker
* _Harold Melvin_: I Miss You
* _Nick Cave_: Into My Arms
* _Patsy Cline_: She's Got You
* _Ronettes_: Do I Love You
* _Stevie Wonder_: I Love Every Little Thing

## genres

📻 https://wfmu.org/ https://www.wrti.org/ https://player.siriusxm.com/#/player/live https://github.com/luigifreitas/CyberRadio https://kpiss.fm/about/ http://radiooooo.com/

* _ambient_: https://www.youtube.com/watch?v=fM6FeOyKV-o
* _generative_: https://www.youtube.com/watch?v=ZwRnrNVUTWM https://news.ycombinator.com/item?id=20514446 https://2018.pygotham.org/talks/creative-music-applications-in-python/ https://medium.com/@metalex9/generating-more-of-my-favorite-aphex-twin-track-cde9b7ecda3a https://www.youtube.com/watch?v=MAYlMcyVZ2k https://github.com/Tonejs/Tone.js https://github.com/supercollider/supercollider/ https://www.youtube.com/watch?v=FVonrx47xHk
* Japanese https://www.youtube.com/watch?v=CpJPnCaIy80
* _musicology_: https://www.pythonpodcast.com/music21-computational-musicology-episode-198/ https://www.hooktheory.com/blog/i-analyzed-the-chords-of-1300-popular-songs-for-patterns-this-is-what-i-found/ https://github.com/dodiku/audioowl http://everynoise.com/#otherthings
* _Spanish_: https://www.nonesuch.com/albums/mexico-real-mexico-music-and-song
* albums are getting longer, Chris Brown album has 45 songs

__Africa__

* _makossa_: Cameroon 80s 🗄 Bébé Manga, Amie
* _soukous_: Congolese rumba; Tabu Ley slower version into faster modern-day stuff; apparently still popular in Colombia https://www.youtube.com/watch?v=ZV_TZumIQuc
* https://en.wikipedia.org/wiki/Miriam_Makeba#Musical_influence

__art__

📺 https://www.youtube.com/channel/UC4ihNhN8iN9QPg2XTxiiPJw/videos

* _pre-8th_: secular styles, unrecorded and w/out notation, are born and die [VG 5] https://www.forbes.com/sites/drsarahbond/2017/11/28/five-ways-to-listen-to-the-music-of-the-ancient-world-today/#148147537d9d
* _8th_: start of polyphony, Church develops notation (necessary bc w/ polyphony, music too complex to remember from memory) [VG 11]
* _medieval_ (10th-14th): monophony of rhythm-less chant and “hazy tonality” (Hildegard) to early polyphony (Machaut)
* _renaissance_ (15th-16th): polyphony clarifies (Palestrina)
* _baroque_ (17th): more contrast, opera emerges; Vivaldi; harmony via interweaving melodies vs. chords https://www.youtube.com/watch?v=VR3o45Pwx9Y 2:20
* _classical_ (18th): harmony, concerto (symphony w/ soloist) is dominant, string quartet emerges; Mozart; orchestra instruments finalize in classical period https://music.stackexchange.com/a/86383/56021
* _romantic_ (19th): music closer to literature, politics; Beethoven
* _modern_ (20th): motifs w/out central melody, 12 tone (avoids key); Schoenberg

* _intermezzo_: denoting pieces that do not serve any particular dramatic function (if appearing in an opera), do not fit any particular predefined dance form (such as a waltz or rondo) and are are intended purely as a musical interlude (some composers actually use interlude instead of intermezzo)

* _chamber music_: small group, basically; ex. Philip Glass, ‘Glassworks'
* _motet_: choral composition w/ no accompaniment
* _oratorio_: orchestra + voices + religious narrative (Handel's Messiah, Marsalis' Blood on the Fields)
* _symphony_: 4 movements; cheerful, brisk, reflective, triumphant; Beethoven
* _tone poem_: 1 movement, based on another piece of art; Liszt

__dance__

📺 Pump Up the Volume

* _big beat_: big drops; Chemical Brothers
* _loose_: r&b —> disco —> house
* _tight_: krautrock —> techno
* _offshoots_: garage (faster house) grime (garage but darker e.g. Wiley) dubstep (grime but bad) https://www.youtube.com/watch?v=CRPuD_F-0Jk
* Newark, Club Zanzibar https://www.youtube.com/watch?v=ldWbZZnFmrI
* _sink_: https://www.residentadvisor.net/features/3588 https://www.residentadvisor.net/features/3540 wonder if they'll hold JC house thing again https://www.youtube.com/watch?v=fPhuS1icMYk
* where DJs get music https://www.youtube.com/watch?v=OCKVJCEAe_8 beatport seems to cater to genres I don't listen to https://www.youtube.com/playlist?list=PLThryQTnOzUaZesUD8vUKY_803mRUs4x7

__Jamaica__

* dembow -> reggaeton
* ska -> rocksteady -> reggae -> dub -> dancehall
* ❓ where does soca fit into all this?

__jazz__

🗄 `100-jazz-albums.pdf`

* standards https://www.youtube.com/watch?v=MPRpac5A_fg 11:00
* _temptation_: jazz requires high technical ability, leading to techique receiving disproportionate attention and music defined by music technique and theory, which attracts a musician audience, and so on in a cycle
* relationship to race, transcription, the academy https://www.youtube.com/watch?v=dD0e5e6wI_A
* _styles_: New Orleans, swing, bebop, cool, modal, hard bop, free, third stream, fusion
* _New Orleans_: 1910s King Oliver 1920s Louis Armstrong; swung quarter notes
* _stride_: 1920s Fats Waller; chord on 2 and 4
* _walking bass_: quarter notes that outline chord progressions

__latin__

📺 Latin Music USA

* _salsa (Fania)_: jazz (Machito) + mambo (Tito Puente, Tito Rodriguez)
* _bossa nova (João Gilberto, Elis Regina)_: jazz + samba (‘a' 1 ‘a' 2)
* _conjunto_: mexican
* _norteño_: tejano

__za__

* _generative_: https://alexbainter.com/
* _new jack_: no melody during verse
* _soul_: https://www.youtube.com/user/TheSoulhawk/videos
* _trip hop_: Portishead, Massive Attack, Tricky
