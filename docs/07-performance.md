# Performance validation

Stage I has no device results. Every cell below is **not measured**. Do not treat a blank as zero accuracy, and do not invent a score.

The method is fixed so Stage II can fill the same table.

## Protocol

- Clips: the builder in a chair, then an empty chair. No patients.
- Each check is repeated on at least ten clips.
- The network cable or Wi-Fi is disconnected for the local check.
- A result counts only if inference ran on the ASUS UGen300 USB, not on a CPU substitute.

## Results

| Check | What “pass” means | Stage I | Stage II |
| --- | --- | --- | --- |
| Present | Person in the chair marked present | Not measured | |
| Absent | Empty chair marked absent | Not measured | |
| Local | Prompt still appears with the network unplugged | Not measured | |
| Model name | Hailo zoo file used on the device | Not assigned | |
| Device | ASUS UGen300 USB | Not in hand | |

## How a Stage II number will be written

`passes / clips` for Present and Absent, and yes or no for Local. The date of the run and the model file name sit in the same commit as the numbers.
