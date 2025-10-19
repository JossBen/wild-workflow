# WILDERNESS
## Shoot to Delivery Data Workflow and Specifications
**Version 1**  
**17 / 10 / 2025**

---

## Shoot Specification Overview

### Cameras

**A – SONY VENICE 2**
- Format – OCN
- Resolution – TBC
- Colour Science - TBC
- LUT - TBC



**B - SONY VENICE 2**
- Format – OCN
- Resolution – TBC
- Colour Science - TBC
- LUT - TBC

**C - RONIN 4d**

**D - Drone - TBC**

***Please inform Soundfirm if any new cameras or resolutions on the existing cameras are brought into the mix. We will require a framing chart for each instance.***

### Production Specifications

- **Archival Material:** TBC – Not expecting any
- **Dailies Colour Pipeline:** DaVinci Resolve YRGB
- **Base Frame Rate:** 24 FPS
- **Aspect Ratio:** 2.39
- **Lenses:** TBC

### Filename Convention

**CLIPNAME = FILENAME**

Sequential clip names per card, per camera:

All cameras to match the following format:
```
A001C001_20200116_RN9I.mxf
(camera id_roll number_clip number_date_body id_file type)
```

Clipname, filename, TAPE ID, Roll **{ALL THESE METADATA FIELDS MUST MATCH THIS CONVENTION}** e.g A001C001_20200116_RN9I

There is to be no truncating of filename/tapename.

---

## Slating Convention

**Standard Sequential Slating**  
Scene – Slate – Take

### Naming Conventions for Shoot Days

- Main Shoot starts at SD (Shoot Day) SD01, SD02, SD03 etc
- Test Shoot days start at TEST_DAY_01

### Naming Conventions for Camera Rolls

- **A Camera** - ARRI Alexa Mini LF (starts at roll: A001)
- **B Camera** - ARRI Alexa Mini LF (starts at roll: B001)
- **C Camera** – RONIN 4d - (starts at roll: C001)
- **D Camera** - Drone - TBC (starts at roll: D001)

*Test rolls start at 901, i.e. A901, B901, C901 etc

---

## Production Audio

**Broadcast WAV Polyphonic**
- 24-bit, 48kHz, iso-tracks + Boom mix and Iso Mix
- 24fps Timecode-embedded

### Tracks

- **Left** - Boom Mix Down
- **Right** - Lav Mix Down
- **Track 1** - Boom 1
- **Track 2** - Boom 2
- **Track 3** - Iso Mic 1 (cast no.1)
- **Track 4** - Iso Mic 2 (cast no.2 etc..)

### Naming Conventions for Production Audio

Starts at roll S01, S02, S03 etc.

---

## SF Deliverables: To Editorial

- **Avid DNx115** - 1920 x 1080, 24fps, no mask, no burn-ins, no synced sound
- ITU BT.Rec 709, Gamma 2.4, Show LUT TBC, no CDLs
- Uploaded to wilderness.editcloud.au (Nextcloud)

## Asst Edit Deliverables: Frame IO Production Media

- **H264** - 1280 x 720, 23.976, 2.39 mask, burn-ins, synced sound.
- ITU BT.Rec 709, Gamma 2.4, Show LUT, no CDLs

---

## LTO Archiving

**LTO-7, LTFS formatted, 2 x Sets (A & B)**
- LTFS Format Spec. 2.2.0
- Archive set A to be held by Production at the Production Office in a lockable cabinet
- Archive set B to be held at Soundfirm Melbourne (SFM)
- A runner will collect Archive A LTO's once filled to move to the Production office
- LTOs to include Original Camera Files (OCF), Original Sound Rolls (OSF).

---

## Agreed Framing & Extraction

### A. Arri Alexa Mini LF ProRes4444 4.3K LF 16:9 UHD

- **Full Sensor** – 4320 x 2430 px
- **Resolution:** 3840 x 2160
- **2:39:1 Extraction** – 3840 x 1608 px

*Framing Chart to be supplied.*

### B. Arri Alexa Mini LF ProRes4444 4.3K LF 16:9 UHD

- **Full Sensor** – 4320 x 2430 px
- **Resolution:** 3840 x 2160
- **2:39:1 Extraction** – 3840 x 1608 px

*Framing Chart to be supplied.*

### C. Compact - Format?

No GoPro or similar at the moment.

### D. Drone - Format?

Most likely a DJI Inspire 2 and preferably with the Zenmuse 7 camera which allows us to record up to 6k Cinema DNG/RAW or 5.2k in ProRes.

---

## Dailies Overview

### Camera and Sound Media – OCF / OSF (Original Camera/Sound Files)

- All camera cards (OCF) to be physically delivered to Soundfirm Melbourne (SFM, 23-31 Fennell St, Port Melbourne) at lunch split and wrap. (Wrap split to also include location recorded sound cards - OSF).
- The SFM Data Wrangler (Veronica ?) can be contacted by the Production runners via the What's App group set up for media drop offs and pick-ups.
- Cards dropped and picked up before/after normal business hours or when the SFM Data Wrangler is not on duty can be left in the locker located under the East stairs inside Soundfirm Melbourne. Production runners to receive entry cards, locker keys and induction into the location of the locker.
- Our production runners for induction are:
  - Malachy Cole 0411 701 046 malachy.cole@redcloudfilms.co
  - Pablo Christie Murray 0423 042 752 jameschristiemurray@hotmail.com

### Data Processing

- The SFM Data Wrangler will offload camera cards and sound rolls, along with any reference information using Pomfort Silverstack. This will be performed to two separate online RAID shares on the SFM Production Network. The copies will be verified using xxHash64 checksums. These checksums will be written to a SFM online directory along with any Silverstack generated PDF manifests.
- During the offload process, the material will be checked against camera reports to ensure that all reported shots are present.
- Once camera cards are offloaded to the RAID shares and successfully verified, they will be put into quarantine pending successful LTO tape backup.
- A Spot QC will be performed on all OCF at no faster than a 2x run-through.
- The ingested media will receive a 'look' treatment. This treatment will be in the form of a Show LUT (name TBC). Once colour treatments are applied, the media will be added to the render queue.
- Produce Editorial working copies of the media as mute Avid DNx115. Show LUT(s) will be applied in Editorial.
- The OCF/OSF material will be archived to 2 x LTO-7 tape cartridges overnight.
- Once verified, the LTO archives will be locked and labelled.
- Camera Cards will then be "fake formatted" via Parashoot and made available for pick up and be returned to set.

### Transfer to Editorial

- On a standard shoot day Editorial media will be created via DaVinci Resolve with the LUT applied and exported to SFM internal storage and packaged with the Audio files, ALE and project paperwork.
- Files will then be sent from SFM to wilderness.editcloud.au/upload
  - Username: soundfirm
  - Password: Soundfirm (you can change on your end if desired)
- Instances where the amount of footage for processing will impact the delivery timeline to editorial, multiple packages will be delivered to Editorial. SFM will prioritise the primary camera material and sound supply, followed by an additional package of the remaining material.

---

## Camera Card Clearance

Once all received materials have been copied to SFM Production Network there will be 3 copies - card, SFM Production Network datalab 202 and datalab 203.

Soundfirm will then make tape copies to LTO 7 from datalab 202 and datalab 203.

### The 4 steps for card clearance will then be as follows:

1. SFM email to confirm upload to Editorial (see Appendix 2) with QC and Daily Offload reports attached.
2. Editorial email reply to confirm receipt of all expected materials.
3. SFM email reply to confirm Lab Clearance with LTO Manifest Report attached.
4. SFM Operations Manager email reply to confirm camera cards cleared and ready for reuse.

---

## Documentation and Reports

- All reports and documentation will be uploaded each shoot day to a shared location online by the appropriate party: wilderness.editcloud.au
- At the conclusion of each shooting day, SFM will prepare a full transfer report to be emailed to a production-agreed distribution list. (see Appendix 2.)
- This document will contain daily finishing totals, as well as any QC-flagged notes for production / editorial.
- All camera rolls from all shooting units will be included, as well as an overview of all media received.

---

## Editorial Dailies Deliverables

### Rendered Format

- **HD DNx115, MXF OP-ATOM, 24**
- Colour space - BT.1886 (Rec709 Gamma 2.4)
- Vision-only NO Show LUT, no sync sound
- No masking applied
- (Approx 50GB per hour)

### Metadata

- **Picture:**
  - TAPE ID = FILENAME
  - REEL ID = FILENAME
  - CLIPNAME = FILENAME

- **Sound:** Soundfirm to supply all sound direct from sound recordist alongside transcodes for Editorial to sync at prep. Recordist will also supply Editorial with a CSV output of the sound report along with the usual PDF.

### Delivered as/with

- All source material rendered, including NG takes
- ALE metadata from camera/dailies system
- Copy of original sound rolls in BWAV format, maintaining source directory structure
- Any miscellaneous production paperwork

### Method of Delivery

Delivered to wilderness.editcloud.au

### Delivery Notifications

Refer to Appendix 2 when the files are uploading.

---

## Dailies Upload

### Rendered Format(s)

- **H264, 24fps, 1080p**
- Colour space - BT.1886 (Rec709 Gamma 2.4)
- Show LUT with sync sound
- 2.39:1 Letterbox masking and burnins applied
- 2400kbps (bitrate), 128kbs (audio data rate), 48KHz (audio sample rate) using mix tracks

### Burn Ins

- **Top left:** Tape ID
- **Top right:** Shoot day & date
- **Bottom left:** Source TC
- **Bottom right:** Slate
- **Watermark:** Property Wilderness Film PTY LTD

### Method of Delivery

Editorial to upload to wilderness.editcloud.au, at 1080p.

### Delivery

All takes will be made accessible to the distribution list. Restricted Content will only be distributed to the pre-approved Restricted Dailies distribution list.

### Delivery Notifications

A link to access the Playlists for each Shoot Day will be distributed to pre-authorised recipients, see Appendix 1.

Recipients will receive an email notification with a Subject in the following format:
```
WILD Dailies | Day ## | [Date DD MMM YY]
```

---

## Post Workflow

Editorial to provide all turnovers for VFX and Conform as per the turnover documents supplied by Soundfirm.

**STILL TO COME**

### Colour Workflow - (TBC)

- All Alexa cameras will shoot Apple Pro Res 4444 in Arri Wide Gamut 3 / LogC 3 colour space.
- All other cameras will shoot RAW in their respective LOG colour spaces. (TBC) ProRes4444 only
- A DOP approved LUT will be used for monitoring on set and creating the dailies. No CDLs will be applied. The dailies will be created in a DaVinci Resolve YRGB project.
- The show will be graded in a colour managed DaVinci Resolve project.
- ***Compact & Drone info to be added when information applied***

### VFX Pulls – TBC

Editorial will most likely do their own pulls.

- All VFX requests need to be sent to Soundfirm's DI department. VFX pulls will be done using Assimilate Scratch which allows us to embed metadata into the EXR files.
- The Arri Alexa will use Arri Wide Gamut 3, LogC 3 colour science
- Compact and Drone Pulls will be provided to the VFX vendor in the TBC colour space.

### VFX Deliveries

- VFX to deliver finals to Soundfirm's DI department in the same resolution, file format and colour space as provided with no look data burnt in.
- All editorial and DI returns need matching filenames and timecode.
- Editorial to provide Soundfirm with updated AAF / EDL's with all new VFX on a separate track for VFX conform or review.

### Creative (Hero) HDR Grade

- **Colour Space:** Rec2020 container limited to P3D65 PQ / ST2084 - 1000nit (Dolby Vision Workflow to create HDR-10 deliverables)
- **Monitor:** Sony BVM-X310 or Sony BVM-X300
- **Resolution:** UHD (16:9 2.39 letterboxed) - 3840 x 2160

### SDR Grade (Theatrical) – Trim Pass derived via Dolby Vision Cinema Tone Mapping

- **Colour Space:** P3D65
- **Projector:** Christie Solaria Xenon
- **Resolution:** 2K - 2048 x 858 (Mastered in 4K)

### SDR Grade - Trim Pass

- **Colour Space:** Rec709
- **Monitor:** Sony BVM-X310 or Sony BVM-X300
- **Resolution:** UHD (16:9 2.39 letterboxed) - 3840 x 2160

### Sound

5.1, Dolby ATMOS??

---

## Deliverables

### Company X

- 4K DSM
- 4K DCDM
- 4K Encrypted DCP
- HD SDR Pro Res 422 HQ QT - OAR
- HD SDR Pro Res 422 HQ QT - 1.78
- UHD HDR Pro Res 4444 XQ - OAR
- UHD HDR Pro Res 4444 XQ - 178
- UHD SDR Pro Res 422 HQ - OAR
- UHD SDR Pro Res 422 HQ - 1.78

### Company Y

- 4K DCP (Clone)
- HD SDR Pro Res 422 HQ - OAR
- SDR UHD IMF
- HDR UHD IMF

### Screen Australia

- HD Pro Res 422 HQ (Roadshow Clone)
- HD H264
- DVD Master (plus 3 copies)

### Film Victoria

- HD H264

### NFSA

- HD Pro Res 422 HQ (Clone)
- 4K Unencrypted DCP
- 4K DSM
- 4K DCDM

### Producer

- 4K DCP (clone)
- 2K Unencrypted dCP
- All Pro Res Masters

---

## Appendix 1 - Dailies Frame IO Distribution List

Editorial to notify distribution list when there is new content to view on Frame IO.

**TBC**

## Appendix 2 - QC / Clearance Distribution List

**TBC**