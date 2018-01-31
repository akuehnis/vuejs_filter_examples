# vuejs_filter_examples

```
Vue.filter('substr', function (value, start, length ) {
  return value.substr(start, length);
});

Vue.filter('number_format', function (value, decimal ) {
    if (isNaN(value)){
        return null;
    }
    return parseFloat(value).toFixed(decimal);
});

// Requires DateService
Vue.filter('date', function(value, format){
    if (null === value){
        return '';
    }
    if ((new RegExp("^[0-9]{4}-[0-9]{2}-[0-9]{2}$")).test(value)) {
        var d = Date.fromFormat('Y-m-d', value);

    } else if ((new RegExp("^[0-9]{4}-[0-9]{2}-[0-9]{2} [0-9]{2}:[0-9]{2}:[0-9]{2}$")).test(value)) {
        var d = Date.fromFormat('Y-m-d H:i:s', value);
    } else {
        console.log('could not create Date from Format');
        var d = new Date();
    }
    return d.format(format);
})
```
