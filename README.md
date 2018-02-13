# Perceptual coupling induces co-rotation and speeds up alternations in adjacent bi-stable structure-from-motion objects

Data and analysis for the __"Perceptual coupling induces co-rotation and speeds up alternations in adjacent bi-stable structure-from-motion objects"__ manuscript currently submitted to _Journal of Vision_.

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
* `Shape` shape used for the block, either `sphere-0500` or `cross-0500`
* `Gap` spatial layout condition for the block:
    * `-0.15`  the _overlap_ condition
    * `0` the _touching_ condition
    * `0.15` the _gap_ condition
* `Unambiguious` ambiguity condition for the block
* `Direction` direction of rotation for the biased object, if applicable. `-1` correspond to the rotation to the left, whereas `1` to the right.

Event-specific columns:
* `Percept` experimental event (`start` or `stop`, resplectively the start and end of the block) or the pressed button (`up`, `left`, `down`, `right`). `unclear` means that no key was pressed at that time. Buttons correspond to the following perceptual states:
    * `left` for both objects the direction of rotation was to the left (i.e., object’s front surface moved to the left)
    * `right` both objects rotated to the right. 
    * `down` the left object rotated to the left, whereas the right object rotated to the right.
    * `up` the left object rotated to the right and the right object rotated to the left.

### Experiment 2    

The original data is stored in Matlab `.mat` files. Same raw data is also stored in a single CSV-file `Experiment 2.csv` with following columns:
* `ObserverID` unique observer ID
* `DisplayType` spatial layout of the two spheres: 
    * `H` horizontally arranged
    * `V` Vertically arranged.
* `RotationAxis` axis of rotation: 
    * `X` horizontal'
    * `Y` vertical
* `Background` background type:
    * `0` uniform
    * `1` textured
* `Distance` distance between the spheres in the units of the radius.
* `Percept` reported percept:
    * `-2` unclear
    * `-1` counter-rotation
    *  `1` co-rotation
* `Time` time relative the start of the block in seconds

## License
All data (and associated content) is licensed under the [CC-By Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). All code is licensed
under the [MIT License](http://www.opensource.org/licenses/mit-license.php).
