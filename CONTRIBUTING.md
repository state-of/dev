# Contributing
All the data is available to contributions, preferable from experts in the relevant topic.

We welcome and encourage:
* adding or updating descriptions
* updates to the data after significant events (e.g. releases)
* addition of items (new entities)
* removing of irrelevant items
* creating an up to date snapshot, by repositioning items

We are open to:
* adding new data (topics and categories)
* changing the chart type
* ...

## Ideas
[WIP] ideas of topics and categories.

## Beginners
## Beginners
If you have little to no experience with github or git, contributing might look a bit daunting. Luckily you can make changes completely from the browser. This introduction [guide](https://guides.github.com/activities/forking/) will help you get started with [forking](https://guides.github.com/activities/forking/), [edittng](https://guides.github.com/activities/hello-world/#commit) and creating a [pull request](https://guides.github.com/activities/hello-world/#merge).

### Chart
To reposition items in the chart, click the menu dots above the chart. Select `Edit Mode`. Drag the dots to a new position. Open the browser developer console, and copy the data and replace items[{...}] with this data.

## Data structure
The structure is setup as following: categories represent a broader subject, referencing to multiple relevant topics. Each topic contains data to visualize the current state of that topic.

A good example of a topic is: [topics/programming-language.json](topics/programming-language.json). That topic is referenced by the category [categories/backend.json](categories/backend.json).

It's best to just browse a bit through the repository to get a quick understanding.

## Data Format
JSON is hard to format by hand, especially combining with markdown. The next version will move to a javascript config syntax, which should make editing easier.

### Chart types
Initially build around the hype cycle curve, it now supports a bell and bubble chart type as well. Bubble should become the default:
![Example](https://cdn-images-1.medium.com/max/800/1*dn274lyUoylpBUFJSSDldg.gif)

1. 'bubble' plots a X by Y graph without a curve
2. 'bell' contains several states and each item sits on a bell curve
3. 'hype' follow the hype cycle curve for each hype cycle phase.

## Attributes
Attributes of the chart.
* title - A reference title
* subtitle - A promotional title. Usually in the form of a question of which the chart is the answer.
* description - A long form description of what the chart answers. Markdown only.
* chart_type - Type of chart to render, either 'bubble', 'market' or 'hype'.
* permanent_id = A permanent slug ID.

### Items
List of the items usually as entities and their attributes to plot.
* id
* title
* description
* axis
    * x [0.0, 1.0]
    * y [0.0, 1.0]
* state
* size

### Axis
Naming of the axis, and its directional meaning.
* x
    * label
    * negative
    * positive
* y
    * label
    * negative
    * positive

### States
The states the chart has. Label and width.

### Size
Determines the size of the bubble.
* title
* value

### Positioning item
The position is determined by:
- 'bubble' a float number [0.0 - 1.0] for X and Y
- 'hype' 'bell' a float number [0.0 - 1.0] for X

## Events [WIP]
Events that impact the items in the charts.
* date (Y-m-d)
* source (link)
* title
* reference_id = to item ID.

## Merging proposal
A commit should be followed up by a merge requests which starts a discussion thread, of which a decision is made to merge or discard.

# Guidelines
1. Don't commit changes that have a sole commercial or promotional intent. General rule is to not add any items to which you are affiliated. Updating inaccuracies or descriptions are allowed and encouraged.
2. Don't be an ass by forcing your personal opinion.

# Future
Looking for a way to make snapshots of the data to allow moving forward/backward into time.
Easy tool to create and edit a great chart, and output JSON.
Optionally looking at changing .json to a .md format.
