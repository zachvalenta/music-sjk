# sw around music library

* _model_: relational
* _interface_: ?

* current headers to store: albums, live, songs, parts
> also store output of file watcher?

* _artists_: The Band, Cody Chesnutt, D'Angelo, Stevie Wonder, Nas, Jay-Z, Andre, TVotR
* _code music_: ambient, drone, idm
* _erosion of ownership_: subscription, DRM, end-user license agreements https://www.eff.org/deeplinks/2017/05/book-review-end-ownership%0A https://news.ycombinator.com/item?id=15862494
* _high points_: Stevie Wonder for the 70s, Wu Tang in 1995, TVotR in the 2000s
* _Philly_: Barbara Mason, Coltrane, Philly Joe Jones, Jaco Pastorius, McCoy Tyner, Roots, The Trammps, War on Drugs, Delfonics, Nina Simone, Tierra Whack
* _playlist_: baby it's you, baby it's me
* _session musicians_: Wrecking Crew, Funk Brothers, Muscle Shoals
* _underappreciated geniuses_: Cody Chesnutt, Jens Lekman
* _upset_: Illmatic intro, Legend, Many Men, Walk, U Guessed It, Mantra, A Lot, Return of the G, Praying for Help, Nowhere2Go, Alright, Yah, Love, Fear, Hail Mary, Heaven
* _lyrics_: Stooges raw power Mac grand finale, Lil Kim queen bitch Jay Elec how great

Big L
> and when it comes to gettin' nookie I'm not a rookie / I got girls that make that chick Toni Braxton look like whoopie - put it on
> everybody wanna be like Mike / but Mike wanna be like L
> Every minute, my style switches up / they say a real man / Won't hit a girl / well I ain't real cause I beat bitches up - danger zone
> I got slugs for snitches / no love for bitches / puttin thugs in pictures / when my trigger finger itches - Jay Z freestyle

Mac grand finale

> And if by chance this is my grand finale / bury me in Allegheny County
> It's the most hated, so faded that I'm bow-legged / don't bathe, gross gang, smell like old lo-mein
> Shit, the flow dangerous, make you wanna do the wave / throw your bitch right off your lap and start a standing ovation
> The most strangest, master of the ceremonies / a fifth of Stoli then it’s only Cher and Moby karaoke
> My bitch a shooter, call her Annie Oakley / get you for a pair of Kobe's, just got out on probation 
> and no famous friends for me, just old faces / I only go places wasted like I'm Joe Namath
> Not a king, I'm no David, music, I'm a crackhead / no hobbies and recreation, don't even know my address
> Self medicate, self education / Rick Rubin showed me transcendental meditation

lifetime
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

moment
* 2003: listening to 'Rich' going into the Lincoln Tunnel
* 2003: turn on 'De-Loused in the Comatorium' in my room, sit down
* 2006: TV on the Radio at Starlight Ballroom, Radiohead at Bonnaroo, Clipse in Pittsburgh
* 2010: Carsick Cars in Beijing
* 2016: Xiu Xiu does Laura and Leland
* 2017: Caravan in my apartment
* 2019: Bruce and Dancing in the Dark at Astor Bar

## tooling

* _streaming_: https://selfhostedsource.tech/category/self-hosted/audio-streaming
* _youtube-dl_: makes Hombrew responsible for ingesting latest version https://github.com/ytdl-org/youtube-dl/issues/20553 seems like Github issues have disappeared; alternative https://github.com/Marethyu12/gotube if 403 run `--rm-cache-dir` https://github.com/ytdl-org/youtube-dl/issues/23638
* download from Soundcloud and Bandcamp https://github.com/Miserlou/SoundScrape
* _metadata_: https://bitheap.org/dnuos/ http://oidua.suxbad.com/ https://www.theverge.com/2019/5/29/18531476/music-industry-song-royalties-metadata-credit-problems http://richardmavis.info/tagging-files
* _NAS (network attached storage)_: aka 'home media server'; options (Plex, cmus remote) https://www.youtube.com/results?search_query=cmus+remote&page=&utm_source=opensearch https://www.youtube.com/watch?v=UJw9YU_SBzo https://blog.dave.tf/post/building-nas-1/ https://www.youtube.com/results?search_query=build+a+nas https://www.youtube.com/results?search_query=buy+a+nas https://kevq.uk/my-home-server-2-months-on/
> all this work just to stream music doesn't make sense, just keep rolling w/ backups and your $60 thumb drive
* _tagging_: http://beets.io/ + Meta ('Benjamin Jaeger' 🗄 `Applications/Meta`) https://github.com/beetbox/mediafile https://musicbrainz.org/

__Looper__

* might be able to just use Audacity https://www.audacityteam.org/ https://duckduckgo.com/?q=audacity+slow+tempo+without+changing+pitch&ia=web
* aka phase vocoder https://github.com/Muges/audiotsm/ https://librosa.github.io/librosa/generated/librosa.core.phase_vocoder.html?highlight=phase#r93e62eaec025-1 https://github.com/haoyu987/phasevocoder https://duckduckgo.com/?q=python+phase+vocoder&ia=software
* Anytune https://apps.apple.com/us/app/anytune-slow-down-music-bpm/id415365180 https://www.youtube.com/watch?v=oM7XmutLszM
* _inspiration_: Wyatt 5 https://wiki.python.org/moin/PythonInMusic https://www.youtube.com/watch?v=1fr_5v6nc-s
* things in this space: https://www.reddit.com/r/Guitar/comments/3v4tql/how_to_slow_down_music_in_order_to_play_along/ https://music.tutsplus.com/tutorials/10-apps-for-slowing-down-solos--audio-7516 Anytune https://www.youtube.com/results?search_query=anytune&page=&utm_source=opensearch Transcribe https://www.seventhstring.com/xscribe/screenshots.html https://wiki.python.org/moin/PythonInMusic
* _features_: loop section (like Steezy) add metronome, slow down (you don't need to warp if Youtube doesn't) https://stackoverflow.com/q/9953219/6813490

__file watch__

poc
```sh
alias mlib="cd /Volumes/MUSIC-LIB && t > ~/Desktop/music-lib-$(date +"%Y%m%d").log"
```

* _sink_: https://github.com/watchexec/watchexec https://facebook.github.io/watchman/ https://github.com/emcrisostomo/fswatch https://vsoch.github.io/watchme/getting-started/ https://github.com/cespare/reflex https://github.com/cortesi/modd  --> `mlib` `os.walk()` https://unix.stackexchange.com/questions/90115/convert-output-of-tree-command-to-json-format/ regex to strip and kebab https://github.com/30-seconds/30-seconds-of-python#kebab https://www.robertchristgau.com/get_gl.php?g=A%2B store library song info as db

__music trimmer__

https://github.com/jiaaro/pydub https://realpython.com/playing-and-recording-sound-python/

```python
from pydub import AudioSegment
song = AudioSegment.from_mp3("april-in-paris.mp3")
first_10_seconds = song[:10000]
repeated = first_10_seconds * 2
repeated.export("mashup.mp3", format="mp3")
```

## cmus

* I wish there was history file
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

* _repeat current_: `ctrl r`
* _continue_: `C`
* _shuffle_: `s`
* _play from_: `m`
* _toggle play from library or playlist_: `M`

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
* _display - time remaining in song_: settings - 'show_remaining_time'
* _display - hidden files_: `i`

## albums

top 10
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

cover art
* Lost in Translation OST Japanese version
* Miles Davis someday my prince will come
* Ohio Players skin tight
* Slint spiderland 
* Diana Ross first album 
* Bobby Timmons little barefoot soul 
* Monica miss thang
* Mike Clark Paul Jackson funk stops here 
* John Prine sweet revenge
* Odetta at the gate of horn

titles
* Kingdom tears in the club
* Ramones too tough to die
* https://en.wikipedia.org/wiki/The_Powers_That_B#Niggas_on_the_Moon
* https://en.wikipedia.org/wiki/Turn_It_Up_Faggot 
* https://en.wikipedia.org/wiki/I_Don%27t_Like_Shit,_I_Don%27t_Go_Outside
* https://en.wikipedia.org/wiki/Who_Is_This_Bitch,_Anyway%3F
* If This is House I Want My Money Back https://www.discogs.com/Various-If-This-Is-House-I-Want-My-Money-Back-III/release/5715012

dance
* _Derrick May_: Live in Sciabecco
* _DJ Richard_: Grind
* _The Field_: Looping State of Mind, Cupid's Head
* _Omar S_: The Best

jazz
* _Chet Baker_: Chet Baker Sings
* _Coltrane_: Blue Train, Love Supreme
* _Ellington_: Money Jungle
* _Horace Silver_: Jazz Messengers, Songs for My Father
* _Kamasi_: The Epic
* _Mingus_: Ah Um
* _Miles Davis_: Sketches of Spain, Bitches Brew

rock
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

r-n-b
* _Anita Baker_: Rapture
* _D’Angelo_: Voodoo, Black Messiah
* _James Brown_: Live at the Apollo
* _Steve Wonder_: Music of My Mind, Talking Book
* _Sly Stone_: There’s a Riot Goin’ On

rap
* _Clipse_: Hell Hath No Fury
* _Game_: Documentary 2
* _Kendrick_: Damn
* _Outkast_: ATLiens, Aquemini, Stankonia
* _Vince_: Stolen Youth
* _Wu_: Only Built 4 Cuban Linx

za
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
* Band and Van Morrison - Caravan
* D'Angelo https://www.youtube.com/watch?v=3woHfDKTjqU
* Fela Kuti https://www.youtube.com/watch?v=zisHSsk9Og0
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

* _titles - songs_: I'm Leaving You Because I Don't Love You

intros
* S Express theme from s express
* Beach Boys wouldn't it be nice
* Diana Ross i'm coming out
* Fucked Up broken head
* Mount Kimbie home recording
* Ghostface back like that

about God
* Stevie have a talk with god
* Al Green god is standing by

piano breaks
* Nick Drake pink moon
* Faces wish ooh la la
* Elliott Smith pitseleh

love
* _Angel Olsen_: Heart Shaped Face
* _CeeLo_: No One's Gonna Love You
* _Girls_: Heartbreaker
* _Harold Melvin_: I Miss You
* _Nick Cave_: Into My Arms
* _Patsy Cline_: She's Got You
* _Ronettes_: Do I Love You
* _Stevie Wonder_: I Love Every Little Thing

top 10
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

dance
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

jazz
* _Coltrane_: Blue Train, Naima, In a Sentimental Mood, Moment's Notice
* _Derrick Hodge_: For Generations
* _Ellington_: Fleurette Africaine
* _Lester Young_: Lester Leaps In
* _Miles_: It Never Entered My Mind, My Funny Valentine, Someday My Prince Will Come
* _Mingus_: Open Letter to Duke
* _Horace Silver_: Calcutta Cutie

pop
* _Baby Shakes_: Love Machine
* _Camera Obscura_: French Navy
* _Kid Wave_: Sway
* _Orioles_: Too Soon to Know
* _Ronettes_: Do I Love You

rap
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

r-n-b
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

rock
* _Angel Olsen_: Heart-Shaped Face
* _Antlers_: Rolled Together, Hotel, Revisted
* _Band_: Band (when you awake, rockin chair)
* _Beach Boys_: Wouldn't It Be Nice
* _Beatles_: I'm Looking Through You, In My Life, I Want You, Helter Skelter, Don't Let Me Down
* _Billy Riley_: Red Hot
* _Black Sabbath_: War Pigs
* _Blondie_: Heart of Glass, Sunday Girl
* _Bowie_: Heroes
* _Broken Social Scene_: Lover's Spit, Cause Time
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

za
* _Arthur Russell_: Wild Combination, Keeping Up
* _Babatunde Olatunji_: Gin Go Lo Ba
* _Billy Boy Arnold_: Wish You Would (Bowie version)
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
* _Patsy Cline_: Strange, She's Got You
* _Red Hot Chili Peppers_: Porcelain
* _Talk Talk_: New Grass
* _Van Morrison_: Caravan, Sweet Thing
* _xx_: VCR, Shelter

folk
* _Arthur Russell_: I Won't Be Around Anymore
* _Bill Callahan_: Riding for the Feeling, One Fine Morning
* _Kelis_: Bless the Telephone
* _Neil Young_: Cripple Creek Ferry
* _Nick Drake_: Pink Moon
* Indian War Whoop

reggae
* _Brian and Tony Gold_: Sweet Baby
* _Clash_: Equaliser
* _Dennis Brown_: Wolves and Leopards
* _Johnny Clarke_: Love Me Forever
* _Junior Murvin_: Police and Thieves
* _Scientist_: Miss Know It All
* _Shabba Ranks_: Peenie Peenie
* _Wayne Smith_: Under Me Sleng Teng
