# Co-rotation dominates perception of adjacent bi-stable structure-from-motion objects

Data and analysis for the __"Co-rotation dominates perception of adjacent bi-stable structure-from-motion objects"__ manuscript currently submitted to _Journal of Vision_.

## Analysis
The complete analysis, including all figures and statistical comparisons, can be found in Jupyter notebooks.

## Data files format

### Experiment 1
Each row corresponds to a single event that occurred during a block.

Session-specific columns:
* `Observer` observer ID, matches the file name
* `SessionID` timestamp for the session start

Block-specific columns:
* `Block` block index
* `Gap` spatial layout condition for the block with `-0.15` corresponding to the _overlap_, `0` to the _touching_, and `0.15` to the _gap_ conditions.
* `Unambiguious` ambiguity condition for the block
* `Direction` direction of rotation for the biased object, if applicable. `-1` correspond to the rotation to the left, whereas `1` to the right.

Event-specific columns:
* `Percept` experimental event (`start` or `stop`, resplectively the start and end of the block) or the pressed button (`up`, `left`, `down`, `right`). `unclear` means that no key was pressed at that time. Buttons correspond to the following perceptual states:
    * `left` for both objects the direction of rotation was to the left (i.e., object’s front surface moved to the left)
    * `right` both objects rotated to the right. 
    * `down` the left object rotated to the left, whereas the right object rotated to the right.
    * `up` the left object rotated to the right and the right object rotated to the left.

### Experiment 2    


 Time of the event __in seconds__, relative to the block start, is stored in `Time`column. Object's location, at the moment of the event, is stored in `RelativeLocation` column: `-1` correspond to the left limit of the trajectory, `0` to the mid-point (screen center), `1` to the right limit of the trajectory. `Direction` column encodes the direction of object's horizontal motion at the time of the event: `-1` to the left, `1` to the right.

Each event is described by a code `Event` and `Value` columns:
* `Block start` block and display onset (empty `Value`)
* `Trajectory limit` object reached the limit of the trajectory and its linear motion was reversed. `Value` encodes new direction of motion: `-1` left (right trajectory limit was reached), `1` right (left trajectory limit was reached).
* `Reverse rotation` vertical motion of all individual dots was inversed to trigger a reversal in the perceived 3D rotation (see Methods for details). Empty `Value`.
* `Percept` percept onset as reported by the participant (via a key press). `Value`  encodes the reported direction of rotation around the vertical axis: `-1` up, `1` down.
* `Block end` end of the block

Columns common for the entire experimental session:
* `Observer` observer ID, matches the file name
* `SessionID` timestamp for the session start

Columns common for the entire block:
* `Block` block index
* `sfmWidth` width of the structure-from-motion (SFM) object _in pixels_. Occluder width corresponded to 150 pixels.
* `showHalo` whether halo around the object was shown (`True`/`False`)
* `playSound` whether the panning sound was played during the presentation (`True`/`False`)

### Experiment 2
Same as Experiment 1, but block-specific `sfmWidth`, `showHalo`, and `playSound` columns are replaced with `Occluder` and `Color`:
* `Occluder` are of the occluding object covered by apertures. `0` means no occluding object, `5` means that aper`1` means that apertures covered 5% of the occluding object, etc. `100` means there were no apertures.
* `Color` color of the occluding object. `y` means yellow, `b` means background color, so that the occluding object fully blended into the background.

### Experiment 3
CSV-file contains data extraced from a corresponding EDF-file. Please refer to the `edf2csv_Events.m` Matlab script in the data folder for details on export. Suffixes __sound__ and __blink__  label files for, correspondingly, sound-only condition and close-eyes-in-response-to-the-tone condition. Please refer to the Methods section for details.

Each row describes a single recorded event:
* `Time` time of the event __in milliseconds__, relative to the start of the block.
* `Block` block index
* `Trial` trial index, trial corresponds to the time in-between to trajectory limits (in-between two `Trajectory limit` events in Experiment 1 and 2)
* `Event` and `Value` describe the specific event as follows:
    * `trial start` start of the trial from the trajectory limit, `Value` matches the trial index
    * `percept` participant pressed the key indicating the percept. `Value` can be either `Up` or `Down`
    * `sound` onset of the note, `Value` specifies its duration, either __1000 ms__ or __1500 ms__.
    * `blink` onset of the blink (observer closed eyes). `Value` specifies the duration of the blink.

## License
All data (and associated content) is licensed under the [CC-By Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). All code is licensed
under the [MIT License](http://www.opensource.org/licenses/mit-license.php).
