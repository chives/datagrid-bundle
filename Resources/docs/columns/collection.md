# Collection

<table>
    <head>
        <tr>
            <td><b>Option source</b></td>
            <td><b>Option name</b></td>
            <td><b>Value type</b></td>
            <td><b>Default Value</b></td>
        </tr>
    </head>
    <tbody>
        <tr>
            <td>Options </td>
            <td>
                <ul>
                    <li>collection_glue</li>
                </ul>
            </td>
            <td>
                <ul>
                    <li>string</li>
                </ul>
            </td>
            <td>
                <ul>
                    <li><code>' '</code></li>
                </ul>
            </td>
        <tr>
        <tr>
            <td>Default Column Options Extension</td>
            <td>
                <ul>
                    <li>label</li>
                    <li>field_mapping</li>
                    <li>display_order</li>
                </ul>
            </td>
            <td>
                <ul>
                    <li>string</li>
                    <li>array</li>
                    <li>integer|null</li>
                </td>
            </td>
            <td>
                <ul>
                    <li><code>$column->getName()</code></li>
                    <li><code>array($column->getName())</code></li>
                    <li><code>null</code></li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Value Format Column Options Extension (Doctrine)</td>
            <td>
                <ul>
                    <li>value_glue</li>
                    <li>value_format</li>
                    <li>empty_value</li>
                </ul>
            </td>
            <td>
                <ul>
                    <li>string|null</li>
                    <li>string|null</li>
                    <li>array|string|null</li>
                </td>
            </td>
            <td>
                <ul>
                    <li><code>" "</code> (empty string)</li>
                    <li><code>"%s"</code></li>
                    <li><code>null</code></li>
                </ul>
            </td>
        </tr>
    </tbody>
</table>

### Usage example

Input class

```php
class News
{
    /* @var string[] */
    public $keywords;
}
```

======
#### Example 1

**Column Configuration**
```php
$datagrid->addColumn('keywords', 'collection', array(
    'collection_glue' => ', ',
    'value_format' => '%s'
));
```

**Input**
```php
$news = new News();
$news->keywords = array(
    'animals',
    'wildlife',
    'Africa
);
```

**Output**
> animals, wildlife, Africa
