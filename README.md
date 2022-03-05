# Camera Printed Music Staves Dataset

The CPMS dataset is a camera-based printed music score dataset under realistic scenarios created by us, which is set up by taking photos with mobile devices under different angles and light conditions. The test set is originate from the public repertoire of the 2020 sight-singing exam at the Wuhan Conservatory of Music in China(http://www.hbea.edu.cn/html/2019-09/12349.html), and we take pictures and label the printed msuic scores.

## Annotation schema

### Directory Structure

Our project adopts the following directory structure

```
CPMS_Dataset/
├── data/
|		├── IMG_1609.jpeg
|		├── IMG_1610.jpeg
|		└── ...
├── label/
|		├── IMG_1609.json
|		├── IMG_1610.json
|		└── ...
```

The data folder stores the pictures of the photographed music scores, and the label folder stores the annotation data. Each music score image corresponds to a json format label.

### Annotation File format Example

```
{
		"0": [
				{
            "x": 125,
            "y": 167,
            "pitch": "G4",
            "duration": 1
        },
        ...
		],
		"1": [
        {
            "x": 111,
            "y": 291,
            "pitch": "C5",
            "duration": 4
        },
        ...
    ],
    ...
}
```

Notes:

- The annotation file is in JSON format, each music score image corresponds to a json format file.

- The top level field `0`、`1`indicates the row index of the staff, usually a staff has 10 lines.

- The field`x`、`y`indicate the coordinates of the upper left corner of the notehead bounding box.

- The field `pitch`indicates the pitch of the note in scientific pitch notation.

- The field`duration`indicates the index of duration classification of the note,and the corresponding relationship is as follows:

  | index    | 0      | 1          | 2         | 3             | 4             |
  | -------- | ------ | ---------- | --------- | ------------- | ------------- |
  | duration | whole  | half       | half_dot  | quarter       | quarter_dot   |
  | index    | 5      | 6          | 7         | 8             | 9             |
  | duration | eighth | eighth_dot | sixteenth | sixteenth_dot | thirty_second |
  
  

​		





