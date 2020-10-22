# jQuery Column HeatMap - Plugin

![](/media/preview.png)

Column heatmap is a simple plugin created for the powerfull javascript lib jQuery, where you can create a table heat map based on EACH COLUMN values.

## Dependencies

* jQuery

## Usage and Parameters

### Basic Initialization
```
$('#TABLE').columnHeatmap({
    columns: [1, 2, 3, 4]
});
```
* The columns parameter expects and array with the indexes of the table columns to apply the heatmap, **first column is key 0**.

### Parameters
| Parameter | Type | Default | Required | Description|
|    ---    | ---  |  ---    |  ---     |     ---    |
| columns | *array* | ``` [] ``` | ✔️ | The columns that the plugin should apply the heatmap, first column is key 0.|
| contrast | *boolean* | ``` true ``` | ✖️ | Change the text color to white if the background color is stronger |
| inverse | *boolean* | ``` false ``` | ✖️ | By default, the highest value receives a red background, and the lowest a green. If is set to true, the logic are reversed |
| animated | *boolean* | ``` true ``` | ✖️ | Fade in the background color |
| animationSpeed | *float* | ``` .1 ``` | ✖️ | Fade in velocity in seconds |
| fn_parseValue | *function* | ``` null ``` | ✖️ | Change the parsing behavior, receiveis the td content, must return and Integer or Float. (example below) |
| colorStartPoint | *int* | ``` 0 ``` | ✖️ | Color offset in HSL color pallete, from 0 to 360. |

### Custom TD Content Parse (fn_parseValue)

Is possible to apply a custom parsing for each column content. By default, is applied a regex to get only numbers, commans and periods of the content.

Regex:
```
/[\d|\-|.|,]+/
```

#### Example
**Parameter:** *text* (Current cell content)
**Return:** *float|int*

```
$('#TABLE').columnHeatmap({
    columns: [1],
    fn_parseValue: (cell_value) => {
        // logic
        cell_value = 1;

        return cell_value;
    }
});
```
