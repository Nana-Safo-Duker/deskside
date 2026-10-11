# Model information

## Job

Binary presence at a chair: person present, or person absent. One person in frame is enough. The model does not name the person.

## Model to use in Stage II

A person-detection model from the Hailo model zoo shipped with the ASUS UGen300 SDK.

The exact zoo name, input size, and file name will be written here after the device and SDK arrive. They are not known in Stage I, and this file does not invent them.

## Why this class of model

The organizer describes the UGen300 as suited to on-device inference, image recognition, and context-aware edge use, with pretrained models available. Presence is that job. A medical classifier is not.

## Runtime

- Accelerator: Hailo-10H inside the ASUS UGen300 USB
- Host: the clinic PC
- Precision and budget: the organizer states up to 40 TOPS INT4 and 8 GB on this class of device
- Network: not required at inference time

## What the model must not do

- Detect a disease
- Read a face as an identity
- Read text on the screen
- Call a cloud API

## Output used by the service

A present or absent flag, plus the vendor confidence score if the zoo model provides one. The lock prompt uses the flag. The score is stored only in the local log, if it is stored at all.
