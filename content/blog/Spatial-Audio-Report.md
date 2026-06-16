*Simon Whittome - May 2026*

_This report was written as a part of the Tonmeister course at the University of Surrey, in the final year module, audio engineering 3_

>[!quote] 
>'There was nothing Lucy liked so much as the smell and feel of fur. She immediately stepped into the wardrobe and got in among the coats and rubbed her face against them, leaving the door open, of course, because she knew that it is very foolish to shut oneself into any wardrobe. Soon she went further in and found that there was a second row of coats hanging up behind the first one. She took a step further in—then two or three steps—always expecting to feel woodwork against the tips of her fingers. But she could not feel it.
>
>"This must be a simply enormous wardrobe!" thought Lucy.'
>
>***C.S. Lewis,
>'The Lion, The Witch and The Wardrobe'***

---
But does it sound like a simply enormous wardrobe?

This spatial audio report examines binaural spatialiser plugins and binaural recording techniques that either have been used, or could be used in the production of audio books / book-based audio experiences. The structure of this report follows an examination of the wider context of spatial audio in the audiobook industry, a critical evaluation of available tools, and a personal attempt at creating a spatial audio book with a critical evaluation of the final product. This report focuses specifically on binaural audio listened to on headphones, reflecting how audiobooks are normally listened to.

Some key questions I have at the beginning of this report include: how are audiobooks consumed, what applications could spatial audio have in the space, and what has already been tried using spatial audio. As this is a *spatial audio* module, only a short time will be spent reviewing the consumption of audiobooks, followed by a more in depth analysis of the tools available and a review of my own production.

---
### Wider context - Audiobooks
Firstly, how are audiobooks consumed? [Tan, 2023] conducted a study examining the attitudes towards audiobooks and how they are consumed. She found that four main groups of people existed: bookworms, non-readers, experience lovers and entertainment seekers. Consistent across three of these groups was an enjoyment of being able to multitask whilst listening, whilst the experience lovers take time out to just listen to an audiobook as an activity in itself. Thus, spatial audio would be best aimed towards enhancing the immersiveness for experience lovers. As this isn't the majority, it makes sense why the standard for audiobooks is still a mono recording of a pleasant voice reading the text. So, has anyone tried to use spatial audio techniques to make an audiobook more engaging?

In 2022, Audible unveiled Dolby Atmos as a new 'gold' standard for audiobooks, and as of May 2026, a collection of 44 audio books with Dolby Atmos available.

Dolby Atmos isn't a traditional channel based format, but rather an object based format. Sounds are treated as objects, and its position over time and audio information are encoded into the format, and a decoder positions that sound according to the user's speaker configuration. The benefit of using a format like Atmos is that it is adaptable across configurations, meaning a down-mix can be created for headphones, 5.1 surround sound, and all the way to large scale formats.

As recently as 2025, Audible released the full cast narrated Harry Potter Collection, mixed binaurally for stereo headphones, and available in Dolby Atmos. It's scored highly in reviews, the market is there, and it is mixed in an immersive format for headphones. I reviewed the opening chapters available for preview, and made note of how spatial audio was used. I listened using typical Bose wireless consumer headphones to replicate how a normal person might hear spatial audio :

1) The narrator is a mono recording, but voiced characters are spatialised and spread out horizontally

2) Diegetic sounds are spatialised. A comparison could be made to the diegetic sounds for film and TV, although the ones present here are more 'obvious' sounding, as they serve the purpose of cluing the listener in to what's going on in the scene

3) Lots of creative sound design. Sound track, special magical sounds, creature sounds, ambience tracks. The soundscapes created give the listener clues to the location of the scene of writing. These aren't obviously positioned in space in my listening experience, and are probably just stereo.

These are all elements I'd like to recreate in my audiobook, with the aim to demonstrate how using spatial audio contributes to improving the overall listening experience.

---
### Binaural audio

To understand how to make the spatial elements heard in the Harry Potter example, it must first be understood how humans perceive the position of a sound source, so that I can reproduce this effect over headphones.

In his book 'Spatial Hearing', Jens Blauert introduces key concepts for understanding how the human auditory system localises sound [Blauert, 1997]. Localisation is the ability to perceive the position of a sound source based on several properties of the way the sound is heard at the ears, properties called 'cues'.

When a sound source is in front of a listener, there is no level difference or arrival time difference between the ears; the sound is the same at both ears. But what about a sound source that is 45 degrees to the right of a listener? The sound will arrive at the right ear first, followed by the left ear after a short delay - this timing difference is known as the interaural time delay (ITD).

A sound source approaching from 45 degrees off the median plane will also be attenuated by an amount determined by the distance of the source from the listener. At large distances, this level difference will be small due to the inverse square law, but in the near field, this will be significant - this is the interaural level difference (ILD).

Elevation perception comes through the filtering of the outer ear, the pinna. When a sound is above a listener, it reflects and refracts around the outer ear geometry before entering the ear - the result is that the pinnae filter the frequency of the sound, with the exact filtering dependent on vertical angle of approach and the shape of the outer ear, head shape and the torso.

ITD and ILD are binaural cues (the difference between two ears) and pinnae filtering is a monaural cue (available to each ear independently). When these cues are recreated over headphones, they give the illusion of virtual sound sources.

Whilst vertical and horizontal direction can be obtained by replicating these cues, how far away a sound is heard is perceived to be is also relevant. One of the strongest cues for distance perception is the sound intensity and reverberation of the environment. Other cues include spectral cues particularly high frequency attenuation for distant sources, especially sources over 15m away. [Chitreddy and Jackson, 2020]

---
### How to actually make it? 

Given this understanding of how humans localise sounds, how can this effect be simulated for virtual sound sources? (that is, sources which are not really present in a listener's environment, but are presented to the listener through loudspeakers or headphones as if they were). Considerations of how sounds are recorded, encoded, and reproduced must be made.

Two main approaches for recording exist:

1) Record audio in a manner which reproduces these localisation cues, baking the spatial information into the audio (binaural recording)
2) Record multiple audio sources with individual microphones, then use tools that simulate localisation cues with DSP. (multi-microphone recording)

Addressing the former approach, the Neumann KU100 dummy head exists for this exact purpose - recreating the localisation cues when recording sound to be reproduced over headphones. Whilst useful, it's also completely limited to non-individualised and static use cases, and only really plausible for headphone reproduction to truly carry across the spatial cues present in the mix.

The latter approach begins to look more promising. By synthesising a spatialised scene using different spot microphones, suddenly the creative opportunities are bursting at the seams. Multi-microphone recording permits scene based encoding, loudspeaker based encoding, binaural encoding, and object-based encoding (in summary, every kind of spatial encoding). Clearly, this is the superior choice for recording with spatial audio in mind, as it keeps the most options open.

 Next, what are the best ways of encoding these multiple sources? To achieve the broadest availability across commercially available devices, object based rendering is clearly the best way forward, offering the greatest number of spatial reproduction pathways. The Audible 'Harry Potter' audiobooks model how this can be done: an object-based encoding mix should be made, with a default binaurally encoded audiobook available for simple headphone stereo playback whilst still maintaining some spatial element.

This means that the most people enjoy spatial audio mixes across platforms (headphones, 5.1).

For this project, the voices were mixed using spatialisation plugins that simulate the positioning of mono audio tracks in 3D space using the aforementioned localisation cues.

---
### What tools did I use?

Once I'd recorded the opening chapter with the voice actors, I got to work testing these recordings. I put the narrator in front of the listener, and tried different positionings using different plugins to create a binaural mix for headphones. Here are the tools I used and what I though about them.

###### 3DTI Spatialisation:

![[Pasted image 20260525223732.png]]

3D Tune-In (3DTI) is a well known library for spatial audio research, as it uses HRTFs to spatialise audio. It offers a variety of generic HRTFs for the user to choose from, room reverberation presets, and a main window for visually positioning sound around the user. The purple dot indicates the position, the blue is elevation.

Helpfully, it allows the user to load custom HRTF files in SOFA and 3DTI format, which I sourced from [this website](https://www.sofaconventions.org/mediawiki/index.php/Files) . I tested with the KU100, KEMAR (normal pinnae size) and the stock HRTFs available in the plugin.

With an anechoic voice sample, the positioning worked well in front of the user, but I didn't find any HRTFs that gave convincing rear perception or elevation perception using this plugin. This may be because it's a non-individualised HRTF, but I found that dynamically moving the voice helped listeners localise sound sources to the rear.
##### DearVR PRO 2:

![[Pasted image 20260525224525.png]]

This looks far better for my use case visually - spatialisation is done through the window on the left, moving the source around. This can be done with the sliders, or visually, and one difference this plugin has straight away is the stereo-width. A low stereo width made the source easier to pinpoint, and a wide source made it as though the sound came from a larger body - the assumption is that the stereo mix controls the L and R nodes visible in the window, and these act as two point sources which have HRTF processing applied to them.

Speaking of HRTFs, it's worth noting that there was no obvious way to use custom HRTFs, and I could not find any documentation, so the assumption is that Dear Reality have used their own proprietary HRTFs made specifically for the plugin - it sound good, but elevation perception didn't seem to be perceptually accurate in my testing.

It also allows early reflection simulation, the ability to make a room for custom room sizes. it's unclear if reverberation is also rendered using an HRTF, but it sounds acceptable for the audiobook use case.

This is the plugin I will use for my audiobook excerpt.

---
### Evaluation of final mix

I created an audiobook excerpt of dialogue between characters in C.S Lewis's 'Perelandra', and used the previously mentioned DearReality PRO plugin to create a binaural mix. I used a BBC recording of this audiobook I owned, which is a typical example of a mono audiobook recording. The downside of this was that the voices for characters were inherently the same base voice, but with enough variation to be acceptable. 

The project was setup in Reaper, and I had 1 narrator channel, 3 dialogue channels, and a range of FX and ambience channels. Each dialogue channel positioned was spatialised so that the characters were 'stood' in front of the listener, and on the left and right. The narrator was not spatialised, and centred.

Firstly, the difference between panning and spatially panning is immediately noticeable. The effect of binaurally spatialised voices is very good! This is notable when compared to my attempts with music, where binaurally panning anything sounded odd and out of place. Voice, specifically reading and spoken word, works very well, but it was only when it was integrated into the soundscape / scene that the spatialisation excelled.

The scene is a somewhat philosophical discussion taking place in a forest, next to a brook. For the dialogue, I chose to not use any of the auralisation or reverberation, as it's a close quarters discussion outside. I experimented with spatially panning rustling tree ambience above the listener, but I struggled to be perceptually convinced by any elevation changes I made with the plugin. Bird sounds were far better - spatialising these gave a good impression of verticality. Using the stereo width feature to create the sound of a brook babbling away was useful in creating ambience that still had a sense of spatial position.

---
### Final notes

Overall, the experience is dramatically better than the original recording, which is in part due to the added effects and ambience. I'd argue that the most important improvement compared to the original, is spatialising the dialogue, which had a significant impact on how immersive the experience was when compared to mono or simple stereo panning.

Binaural plugins were generally not useful to me for mixing music spatially, however audiobooks are a fantastic opportunity for the technology to shine!
### Bibliography

Blauert, J., 1997. _Spatial hearing: the psychophysics of human sound localization_. MIT press.

Chitreddy, S. and Jackson, P., 2020, December. Source distance perception with reverberant spatial audio object reproduction of real rooms. In _Forum Acusticum_ (pp. 2079-2086).

Tan, E.K., 2023. _Sound, stories, and psychology: The perceptions and motivations of audiobook consumption_ (Master's thesis, Brigham Young University).