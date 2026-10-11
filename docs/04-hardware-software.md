# Hardware and software

## Selected device

ASUS UGen300 USB AI Accelerator.

The M.2 module was not selected. A USB accelerator can be used from a laptop. The contest form does not allow this choice to be changed after submission.

## What the organizer provides if the team is shortlisted

One ASUS UGen300 for prototyping. Lightning finalists keep the device. Shipping is announced by the organizer. Stage I does not depend on that shipment.

## Host

- A Windows or Linux laptop in Kumasi
- One USB port for the accelerator and one for the webcam
- Python 3 for the service that reads the camera, calls inference, and shows the prompt
- No cloud GPU and no account with an inference vendor

## Software boundary

| Piece | Where it runs | Stage |
| --- | --- | --- |
| Camera capture | Clinic PC | I can simulate with a webcam |
| Presence model | UGen300 USB | II only |
| Lock prompt and local log | Clinic PC | I can simulate the prompt |
| Uploader | None | Not in the design |

## Stage I simulation

A laptop script may label a frame “present” or “absent” by hand, or with an ordinary open model on the CPU, solely to test the prompt. Those labels are not Hailo output and are not written into the performance table as device results.
