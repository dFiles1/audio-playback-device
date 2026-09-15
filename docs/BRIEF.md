# Audio Playback device

I wan a audio playback device  whit audio input and aoudio output, Input is supos to byepas Audio and lover the volume when MP# is playd insid the device, it needs to be linux
analog input
analog output
Small formfactor passiv cooling
2 GB RAM
16 GB onboard eMMC

Core function:
- Continuous stereo analog Line In
- Continuous stereo analog Line Out
- Full-duplex audio operation
- Local playback of stored audio files
- Software-controlled mixing of local audio with the incoming audio signal
- Software-controlled ducking of the incoming audio while a message is played
- Automatic return to the normal input level after playback

The unit must be designed for reliable 24/7 commercial operation.

Hardware requirements:

Processor / platform
- Linux-capable embedded processor or SOM
- Sufficient performance for audio passthrough, local media playback, networking and our application
- Approx. 2 GB RAM is a suitable reference point
- Prefer integrated eMMC storage, approx. 16 GB or more
- No requirement for Wi-Fi or Bluetooth

Audio
- Stereo analog Line In
- Stereo analog Line Out
- Full-duplex ADC/DAC
- Input and output must be independently accessible from software
- Software-controllable input gain preferred
- Software-controllable output level preferred
- Suitable line-level audio performance for commercial AV use
- Low latency through the input/output path
- Good SNR / THD performance
- Local MP3 playback required
- WAV support preferred

Network
- 1 x Ethernet RJ45
- Gigabit Ethernet preferred but 100 Mbps would likely be sufficient
- PoE is desirable as an option if it can be integrated cost-effectively

Power
- External PSU as standard
- PoE option preferred if practical
- Automatic restart after power loss

Storage
- Integrated eMMC or equivalent
- No SD card or USB flash drive as the permanent system storage

Reliability
- Designed for continuous 24/7 operation
- Hardware watchdog preferred
- Good thermal design for passive operation if possible
- Long-term component availability is important

Connectors / enclosure
Preferred rear panel:
- 2 x RCA Line In (L/R)
- 2 x RCA Line Out (L/R)
- 1 x RJ45 Ethernet
- Power input

All audio connectors should preferably be located on the rear panel.

Mechanical:
- Compact black metal enclosure
- Suitable for OEM branding
- Final dimensions to be proposed by Copperhead based on the PCB design

Fail-safe option:
We would also like Copperhead to evaluate a hardware bypass function where Line In can pass directly to Line Out if the unit loses power or in the event of a critical hardware failure.

Software access:
We will develop the application software ourselves.
We therefore require:
- Linux support
- Audio drivers
- ALSA or equivalent low-level audio access
- Documentation for the audio codec and mixer controls
- Ability to install and update our own software image

Expected first production volume:
- Initial production: approximately 150–200 units
- Lower recurring annual volumes expected after the first batch

Development approach:
We would like to start with:
1. Hardware architecture proposal
2. Schematic and PCB design
3. Prototype PCB
4. Functional testing
5. Small pilot batch
6. Production-ready revision

Please provide:
- Recommended processor / SOM
- Recommended audio codec
- Proposed PCB architecture
- Estimated development/NRE cost
- Estimated prototype cost
- Estimated unit price at 50 / 100 / 200 units
- Estimated development timeline
- Any expected certification requirements
- Long-term component availability information

The final product will be branded as:
OneDisplay AudioPlayer
Product family: ONEAUDIO by OneDisplay

Jag skulle också lägga till en enkel blockbild, för den gör projektet mycket lättare för en kretskortsdesigner att förstå:

LINE IN L/R
    │
    ▼
ADC / AUDIO CODEC
    │
    ▼
CPU / SOM
    │
    ├── Local audio playback
    ├── Mixing
    ├── Ducking
    ├── Network control
    └── Local storage
    │
    ▼
DAC / AUDIO CODEC
    │
    ▼
LINE OUT L/R

Ethernet ─────► CPU
eMMC ─────────► CPU
Power ────────► System

Optional:
LINE IN ──► FAIL-SAFE RELAY ──► LINE OUT
