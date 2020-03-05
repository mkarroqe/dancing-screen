# The Dancing Screen
Presenting my Senior Design Project: *Teaching an AI to dance through Fortnite videos.*
All work is being done through Google Colab notebooks.

# Input Data
My training data is extracted from this `51:52` minute [complilation video](https://www.youtube.com/watch?v=R7qdgPkPsuQ) of **146** Fornite dances. I am extracting one frame every 2 seconds for a total of **186,720** images.

# Frame Extraction Pipeline
Before my frames are fed through my model, they are converted into binary images:
| Before | After |
| :-: | :-: |
| ![original image]("examples/orig.png") | ![binary converted image]("examples/bin-conv.png") |

| | Step | Result |
| :- | :- | :-: |
| 1 | Increase contrast to reduce background gradient to blue and cyan pixels | ![contrast image]("examples/contrast.png") |
| 2 | Remove `blue` and `cyan` pixels and replace them with `white`. | ![blue and cyan free image]("examples/no-blue-cyan.png") |
| 3 | Remove remaining intermediary `blue` hues and replace them with `white` pixels. |![no blue hues image]("examples/no-blue-hues.png") |
| 4 | Now that the background is isolated, convert all other pixels to `orange`. | ![final image]("examples/final.png") |
| 5 | Finally, the image is cropped to remove the sidebars. | ![cropped]("examples/cropped.png")
