# API reference for Angular Accordion

### Import module
you need to import Accordion module in app.module.ts:
<pre><code>import { AccordionModule } from 'accordion/accordion.module';

@NgModule({
  ...
  imports: [AccordionModule, ...],
  ...
})</code></pre>

### Usage 
<pre><code>    &lt;accordion&gt;
        &lt;expansion-pane&gt;
            &lt;expansion-panel-header&gt;
                // Header content
            &lt;/expansion-panel-header&gt;
            &lt;expansion-panel-description&gt;
                // Description content
            &lt;/expansion-panel-description&gt;
        &lt;/expansion-pane&gt;
    &lt;/accordion&gt;
</code></pre>

### Methods available to accordion
<table>
    <thead>
        <tr><th>closeAll</th></tr>
    </thead>
    <tbody>
        <tr><td><p>Closes all enabled accordion items in an accordion.</p></td></tr>
    </tbody>
</table>
<table>
    <thead>
        <tr><th>openAll</th></tr>
    </thead>
    <tbody>
        <tr><td><p>Opens all enabled accordion items in an accordion.</p></td></tr>
    </tbody>
</table>
<table>
    <thead>
        <tr><th>multiple</th></tr>
    </thead>
    <tbody>
        <tr><td><p>accordion should allow multiple expanded accordion items simultaneously.</p></td></tr>
    </tbody>
</table>

### using loop
<pre><code>    &lt;accordion [openAll]="true"&gt; // pass input in boolean
        &lt;expansion-pane *ngFor="let value of values"&gt; // 
            &lt;expansion-panel-header [open]="value.open"&gt; // to open particular (input of boolean)
                {{value.header}}
            &lt;/expansion-panel-header&gt;
            &lt;expansion-panel-description [open]="value.open"&gt;
                {{value.description}}
            &lt;/expansion-panel-description&gt;
        &lt;/expansion-pane&gt;
    &lt;/accordion&gt;


values: Array<Object> = [
    {header: 'Expansion panel one', description: 'Expansion description one', open: false},
    {header: 'Expansion panel two', description: 'Expansion description two', open: true},
    {header: 'Expansion panel three', description: 'Expansion description two', open: false}
  ]
</code></pre>