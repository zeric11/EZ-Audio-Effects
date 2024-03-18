# EZ Audio Effects

Eric Zmitrovich


## How to Build and Run

1. Download this project.

2. Download the [JUCE](https://juce.com/download/) framework.

3. Open and save `EZ-Audio-Effect.jucer` using Projucer.
    Projucer can be found in `JUCE\extras\Projucer\Builds`. 
    Select the build according to your operating system.

4. Build and run the project.


## Project Description

This audio plugin provides an equalizer and a reverb function.

The equalizer allows the user to set a low and high-cut filters, 
and a "peak" parametric band with parameters for peak frequency,
peak gain, and peak width.
The low-cut filter ranges from frequencies of 20-2000 Hz.
The high-cut filter ranges from 2000-10000 Hz.
The peak filter ranges in frequencies between 20-10000 Hz,
can have a gain of -24 dB to 24 dB,
and can be scaled from a tenth of its width to ten times it width.

The reverb functionality allows the user to set a reverb value
between 1-100.  
The reverb consists of 5 parameters:
    
* Room size
* Damping
* Width
* Wet level
* Dry level

For simplicity, the reverb value is used to scale
all of these parameters simultaneously.


## Testing

To test this project, I used the JUCE Audio Plugin Host 
with the [vstPlayer](https://miraxlabs.com/products/vstplayer/).
The Audio Plugin Host is located in `JUCE\extras\AudioPluginHost\Builds`.
The filter graph I used is located in `Filtergraph.filtergraph`.


## Project Reflection

This project did not go especially smoothly 
and I'm overall pretty disappointed with how much 
I was actually able to finish.
I had originally planned on writing the plugin's audio effects
from "scratch" in C++. 
However, whether it be my unfamiliarity with JUCE 
or some other reason,
I was unable to get my custom effects to work with JUCE.
Therefore I ended up using JUCE's 
[DSP](https://docs.juce.com/master/tutorial_dsp_introduction.html) 
module implement the audio effects. 
It should be noted that I followed 
[this tutorial](https://www.youtube.com/watch?v=i_Iq4_Kd7Rc)
to guide me through the creation of a JUCE audio plugin.
Thus much of the equalizer functionality mimics that of
[this project](https://github.com/matkatmusic/SimpleEQ/tree/master).
I added reverb functionality using the 
[dsp::Reverb class](https://docs.juce.com/master/classdsp_1_1Reverb.html)
following [this example](https://github.com/szkkng/simple-reverb/tree/main).
I also attempted adding in the
[dsp::Phaser](https://docs.juce.com/master/classdsp_1_1Phaser.html)
and [dsp::Compressor](https://docs.juce.com/master/classdsp_1_1Compressor.html)
modules, however I was wasn't get them to compile with the project.

I hindsight I shouldn't have chosen to work with JUCE for this term.
The majority of my effort working on this project was spent wrestling 
with the JUCE framework.
Whatever programming I actually did was mostly configuring JUCE modules.
I only finished 2 of the 4 audio effects I had originally planned on,
and didn't I get to implement the equalizer and reverb the way I wanted to.


## License

See the [LICENSE](LICENSE.md) file for license rights and limitations (MIT).


### Resources Used

https://docs.juce.com/master/tutorial_dsp_introduction.html

https://www.youtube.com/watch?v=i_Iq4_Kd7Rc

https://github.com/matkatmusic/SimpleEQ/tree/master

https://github.com/szkkng/simple-reverb/tree/main

https://docs.juce.com/master/classdsp_1_1Reverb.html

https://docs.juce.com/master/classdsp_1_1Phaser.html

https://docs.juce.com/master/classdsp_1_1Compressor.html

https://github.com/matkatmusic/AudioFilePlayer