# Creating a Bar Chart

## Using barChart Service
Inject the service in your component
<pre><code>
import { chartService } from '../services/bar-chart-service'; // path may vary
</code></pre>

to create bar chart , input should be of Array of object

### Format of input for baarchart
<pre><code>barchartinput: any = [ { value: 100 }, { value: 75 }, { value: 25 }, { value: 20 }, { value: 50} ] // or
barchartinput: any = [ { value: 100, style: {color: 'red'} }, { value: 75 }, { value: 25, style: {color: '#cdcdcd'} }, { value: 20 }, { value: 50} ]</code></pre>

### Use service to create chart
<pre><code>this.chartService.createBarChart('selector', { inputData: this.barchartinput } )

selector - where to append the bar chart
it may be 'class' or 'id';

if you want to append the bar chart to particular &lt;div class="classsvggtoappend"&gt; or &lt;div id="idsvgtoappend"&gt;
it should be 

<pre><code>this.chartService.createBarChart('.classsvggtoappend'  - class="classsvggtoappend"

this.chartService.createBarChart('#idsvgtoappend'  - class="idsvgtoappend"
</code></pre>

That's it bar chart will get generated to the selector

if you want to customize styling, that also possible

By default

svg width would be selector width (div block width)

svg height would be 250

bar chart color would be of black

### Customize styling
<pre><code>
ChartInput {
    xAxisPosition : string | number; // optional
    yAxisPosition : string | number; // optional
    inputData : {                   // mandatory to draw chart
        value : number;
        style ?: {                  // optional
            color: string           // if you want to customize single bar
            }
        }      
    configData : {
        width : number,            // optional
        height : number,           // optional
    };
    xAxisConfig : {               // optional
        domainMinVal : number;  // x axis scale starting value
        domainMaxVal : number;  // x axis ending value
        ticks : number;         // no of points to be drawn in x axis 
        };  
    yAxisConfig : similar to xAxisConfig;
    styles : {                   // you can add these all style value if you customize
        borderRadiusX : number;  // optional
        borderRadiusY : number;  // optional
        width : number;          // optional
        height : number;         // optional
        fill : string;           // optional
        borderColor : string;    // optional
        axisX : number;          // optional
        axisY : number;          // optional
        strokeWidth : number;    // optional
        };
}
</code></pre>