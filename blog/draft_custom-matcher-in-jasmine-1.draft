---
published: false
categories:
  - sample
---

This is a draft sample


```javascript
beforeEach( function(){
    window.jasmine.addMatchers({
      toEqualAlerts: function() {

        return {
          compare: function(actual, expected) {
            expected = expected || '';

            var pass = actual.length  === 1 && actual[0].type === expected[0].type &&
              actual[0].msg === expected[0].msg;

            return {
              pass: pass,
              message: pass ? 'Ok' : 'Ko'
            };
          }
        };
    }});
  });
```

TODO Expand around here: http://jsfiddle.net/n0dhrwq2/1/

Also explained here: http://pivotallabs.com/writing-beautiful-specs-jasmine-custom-matchers/

Explain differences in jasmine 1.3 and 2.0: http://jasmine.github.io/1.3/introduction.html#section-Writing_a_custom_matcher, http://jasmine.github.io/2.3/custom_matcher.html
