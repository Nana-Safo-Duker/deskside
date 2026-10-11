# Architecture

The diagram is [architecture.svg](architecture.svg).

## Flow

1. A USB webcam looks at the chair.
2. Frames go to a Python service on the clinic PC. They are not uploaded.
3. On Stage II hardware, inference runs on the ASUS UGen300 USB accelerator (Hailo-10H).
4. The model returns person present or person absent.
5. If the person is absent and the operating-system session is still open, the service shows a local lock prompt.
6. A staff member locks the session or dismisses the prompt. The service writes a local log only: time and present or absent. No image is kept.

## Stage I substitute

The accelerator is not available in Stage I. A laptop can simulate the same decision with a placeholder label so the prompt and the log can be checked. That simulation is not a Hailo result and is not reported as one.

## What is outside the box

- Disease detection
- Face identification
- Reading a medical record
- The GeneHus genomic risk score
- Any cloud model
