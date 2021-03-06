New FW release
Version v1.1-31
Changes:
- Bug solved: modulation console command does not work.

New FW release
Version 1.1-26
Changes:
- Bug solved: tinySA crashes when waterfall enabled and scanraw requested
- Added  MARKER/MARKER OPS/ -> REF LEVEL sets the ref level to manual just above the level of the selected marker

New FW release
Version 1.1-24
Changes: 
- AM detection will be disabled when setting AGC to manual (on or off)

Keep in mind the AM correction only happens in the NEXT sweep after the "AM" warning appears.
Every 50 sweeps the AM detection is restarted
Consider setting sweep speed to FAST when measuring with RBW = 3kHz (and even FAST SPEEDUP to 10)

New FW release
Version v1.1-23
Changes:
- MEASUREMENT/FM now measures the actual frequency deviation for modulation frequencies between 1kHz and 2.5kHz and deviations from 3kHz to 500kHz 
- Improved touch calibration markers
- actual 10MHz frequency correction value now stored in config and saved over reboot(this implies your current config will be erased when you upgrade to this FW). Be careful. Entering a WRONG frequency will render a tinySA useless and will require a restore factory settings.
- Marker center zoom now also works for a dragged or searched marker (e.g. when the marker is not in tracking mode) as long as the marker is positioned on a (local) maximum
- Exiting measurement no longer resets all settings

Feedback welcome!!!!

New FW release
Version v1.1-22
Change:
- After MARKERS/MARKER OPS/->CENTER the tinySA goes into auto-center-mode as long as you do NOT use any menu and the lever is automatically set to zoom-span-mode

When using the lever to zoom in/out the selected marker will stay in the middle of the screen whenever possible in the min/max frequency range.
Is this usable?

New FW release
Version v1.1-21
Changes:
- Automatically detect AM signal and adapt settings

WARNING: This is an experimental feature and I need your opinion

When the span is below 300kHz and the signal above -40dBm AM auto detection is active. Once it detects an AM signal it will activate special AM mode.
A red "AM" warning will appear in the status panel and the AGC/LNA setting will be optimized for AM signals
This mode is canceled when the max signal is below -40dBm and the warning text disappears, otherwise it will stay on even when the signal is no longer AM modulated!
Everytime a new setting is applied by the user the AM mode is canceled and auto detection will restart.

As a consequence the first sweep after any change of settings will NOT be optimized for AM and can show the well known AM modulation artifacts. Once detected, the next sweep should be OK.
Incorrect AM detection may be possible and I need to know under what conditions this is happening.

As stated, highly experimental and I probably missed some side effect somewhere. Your testing and feedback is most welcome.

New FW release
Version v1.1-15
Changes:
- The AM measurement mode now calculates the modulation depth based on the two sideband markers.
- The -3dB width measurement is made more robust and accurate

A small warning w.r.t the AM depth measurement. Below 40% depth the measurement reports too high values and below 30% depth the measurement may fail completely.
But as I assume people measuring the modulation depth of an AM signal are supposed to understand how the calculation works, I hope this is not a serious issue.

New FW release
Version v1.1-13
Changes:
- Added a check and error message when no connection between present between high and low connector

New FW release Version v1.1-12
Changes:
- Fix power calibration
Please do not use version v1.1-11 as Power calibration does not work

New FW release
Version v1.1-11

Changes: 
- Selftest extended with attenuator test testing all attenuator internal switches. 

New FW release
Version v1.1-9

Changes:
- Disabled serial console due to insufficient space
- Added THD measurement so MEASUREMENT/MORE menu

The THD measurement gives the % TDH of the signal that is under the first marker by summing the power of all harmonics of the signal under the first marker in the current scan
The maximum number of harmonics you can take into account is about 30 so with a full span in low mode you can measure the THD of the cal output at 15MHz and 30MHZ but not 10MHz or lower.
For lower frequencies reduce the span till the THD measurement appears.

Can someone check if the measured number is about correct?

New FW released
Version v1.1-7
Changes:
- Serial port integrated
- Offset console command added to support External Amp setting from tinySA-App

New FW release
Version v1.1-5

Changes:
- Solved a crash in the frequency menu
- Corrected various errors in FM modulation. (shifting, wrong deviation)

FM modulation should now work correctly for both low and high mode over the entire frequency range.
Be aware: In low mode around 46MHz and in high mode around 480MHz the fm modulation way deviate a bit due to complex PLL switching.

New FW release
Version: v1.1-4 

Changes:
- The AM modulation depth increased to 30%
- NFM deviation increased to 5kHz
- Modulation frequency limits set to 100Hz..6kHz

I will be making a video showing the use of the modulation on the low output and the analysis of the modulation using a tinySA

New FW release
Version v1.1-2

Changes:
- The console command "Marker {number} {value}" now accepts either a index (if below sweep points) or frequency as value

Examples:
>marker 1 100
sets marker 1 to index 100 (if sweep points > 100)
>marker 1 100M
sets marker 1 to 100M (if within sweep range)

If frequency is outside sweep range nothing happens.
Setting the marker to an index or frequency disables tracking

New FW release
Version v1.1

Changes:
- Add option to set the AM or FM modulation frequency. 
- Option to directly set the frequency of a marker instead of searching or moving
- Clean menu when switching to waterfall
- Waterfall now working for all sweep points settings


The modulation frequency can be set over a broad range but is only fairly accurate (+/- 1%)  between 100Hz and 7kHz

New FW release
Version V1.0-99

Changes: 
- Waterfall now also works for 101 and 51 sweep points
- Bottom level indicator removed in waterfall mode
- Menu remainder cleared in waterfall mode
- New MARKER/MARKER SEARCH/ENTER FREQUENCY to set active marker to specific frequency

As I am still traveling only limited testing done.

New FW release
Version V1.0-96

Changes:
- Waterfall now can be in 3 states: off, small and big.
- New expert config options: set minimum horizontal gridlines
- New expert config options: display HAM bands
- Dragging a marker switches off the tracking attribute

As I am still traveling this release has seen a bit less testing. Don't use if your tinySA is mission critical and you have difficulty going back to previous release.

New FW release
Version V1.0-91

Changes:
- MEASURE menu splitted over two menus so the BACK option is visible
- marker {id} peak console command added. 
- caloutput console command added

The marker peak command will make the {id} marker active, position it on the strongest signal and output the marker info
The caloutput command disables or sets the output frequency in MHz
The wiki is updated with these new commands

New FW release
Version V1.0-86

Changes: 
- Added a frequency per division indicator at the bottom
- Increased the minimum number of frequency grid lines to be shown 

New FW released
Version V1.0-84

Changes:
- Added 4 measurement functions: SNR, -6dB width, AM and FM

See the video demonstrating these new options starting here: https://youtu.be/ioM0Si3qI-Y?t=626

As I am no measurement expert I made some liberal use of names.
SNR can be used to measure the difference between a signal and the noise floor
-6dB width can be used to measure the width of an occupied frequency band.
AM does some careful AGC/LNA setting optimization to help observe AM modulation
FM does a quick setting to observe FM modulation.

In case you have suggestions on how to improve these function or for other measurement functions feel free to provide feedback.

New FW release
Version V1.0-82

Changes:
- Restoring a preset that uses a different mode is working again.

Be aware that part of a preset is the stored trace. So if you want to keep a measurement for a long time (e.g. survive a power cycle or an empty battery) do a STORE TRACE and after that STORE into a preset.
Once you do a LOAD the stored trace will appear again.

New FW released
Version V1.0-81

Changes:
- Corrected a number of marker frequency bugs.

I must have been interrupted during the updating of the marker frequency mechanism and forgotten to finish it.
A number of marker frequency bugs have been solved. Let me know if there still are remaining

New FW released
Version V1.0-80

Changes:
- Fixed a crash when touching in empty space below an active menu
- Improved auto level handling, tell me if you notice any unwanted difference
- STORE STARTUP is now used at startup. This could cause problems with starting the tinySA. Let me know it you experience startup problems.

New FW released
Version V1.0-77

Changes:
- Show "Mask: ON" in status panel when mirror masking is active
- Take high mode input attenuation into account when overriding AGC or doing mirror masking

New FW release
Version V1.0-76

Changes:
- Removed the 1kHz frequency grid as it did not add value
- Corrected a bug causing spur avoidance to fail when the manually selecter RBW was smaller than the automatic selected RBW
- Implemented an AGC override in high mode to avoid overload of the IF
- Added a user selectable mirror masking option in high mode

These are some complex changes so I'd like to hear if this all went well.

The spur avoidance table is filled till 100MHz. Not sure if there are any relevant spurs at higher frequencies.
Ingress from strong transmitters and the remaining MCU clock harmonics are not impacted by spur removal as these are actual signal.
If you still see real spurs let me know the start/stop frequency and the active RBW and preferably send also a screen capture

The tinySA high mode had big problems showing a strong signal in a small span. In this case a 300MHz signal at -50dBm

https://groups.io/g/tinysa/message/893?p=,,,20,0,0,0::Created,,Version+V1.0,20,2,0,76686606

To the right of the actual signal at 300MHz you see some disturbance and at 301.8MHz there is a mirror of the 300MHz signal

First step implemented is an override of the automatic AGC, this cleaned up much of the disturbances between the actual signal and the mirror

https://groups.io/g/tinysa/message/893?p=,,,20,0,0,0::Created,,Version+V1.0,20,2,0,76686606

The steps you see are due to the limited granularity of the AGC override and are unavoidable. But these also help to recognise some intervention is happening.

The second step has been to add a MIRROR MASKING in the high mode FREQ menu. When enabled this forcefully removes all signals that could have been caused by mirrors

https://groups.io/g/tinysa/message/893?p=,,,20,0,0,0::Created,,Version+V1.0,20,2,0,76686606

The signal at 301.8MHz is replaced by a constant level plateau so you can see when this is done.

The MIRROR MASKING may fail in certain situations. Let me know if it is usable

If the signal is very strong all will fail but you should get an overload warning.

Feedback is welcome.

New FW released
Version V1.0-69

Changes:
- Removed the modulation interruption causing a rather unpleasant sound

During one of the recent code changes a bug was introduced that caused the modulation to be interrupt a couple of times per second which made the modulation rather unpleasant to listen to.

New FW release
Version v1.0-67

Changes:
- Updated spur avoidance table

After receiving some feedback about possible spurs I made an update of the spur avoidance table
This update could make the scanning a little bit slower.

New FW released
Version V1.0-66

Changes:
- Improved auto attenuate algorithm

The new auto attenuate algorithm has more resolution (1dB i.s.o. 5dB) and updates only once per second to avoid quickly jumping noise floors when scanning in fast mode.

New FW released
version v1.0-64

Change:
- Removed the 2.4kHz auto RWB setting

A youtube reviewer discovered the manual 3kHz RBW provided better narrow span results compared to the automatic 2.4kHz RBW so I removed the 2.4kHz RBW

New FW released
version v1.0-63

Change:
- The target maximum level for the auto attenuation is changed from -20dBm to -30dBm

In one of the user videos I noticed that, when not very familiar with the inner workings of a spectrum analyzer and relying on the auto attenuation functionality, it is important to ensure minimum internally generated harmonics.
This changed setting will raise the noise floor with 10dB with stronger signals but those that know what they are doing and in need of a low noise floor and not concerned about possible internal generation of harmonics can always switch  to manual attenuation.

New FW released
Version v1.0-62

Changes:
- Bug solved: trace store command not working
- Bug solved: Overload flashes in normalized mode
- Normalize activation now asks for reflevel and sets reflevel to manual
- save/recall [id] command added, does store/load of preset (yes, confusing....)

New FW released
Version v1.0-61

Changes:
- After a marker search using the menu, a marker can be moved to any position using the lever.
- When the sweep is paused you can directly select a marker as active marker by touching the marker info and this is reflected in the marker info

New FW released
version v1.0-49

Changes:
- Corrected a rounding error in the level calibration causing up to 1dB level error

Due to a data format change you will lose your configuration information. If you have made any changes you should redoc these after updating.
Both high and low mode level calibration should be re-done using either the built-in calibration source or an external known level signal.
The calibration error off factory should be less then 2dB so after this FW update your levels should be within 2dB without calibration.

Version v1.0-37
For updating see: https://tinysa.org/wiki/pmwiki.php?n=Main.UpdatingTheFirmware

Changes:
- completed the 3D conversion with radio buttons and checkmarks (DiSlord)
- Now 51,101, 145 and 201 scan points possible
