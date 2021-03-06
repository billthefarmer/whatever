Whatever-o-meter
================
![Whatever-o-meter](https://raw.github.com/billthefarmer/whatever/master/wordpress/images/Whatever.png)

## Description
Whatever-o-meter is a WordPress plugin and Hugo shortcode that shows a
tachometer-like dial with a pointer, asks a series of predefined
questions which are answered by moving a slider, shows one of several
predefined results, and moves the tacho pointer to a position
determined by the value of the result.

The plugin uses a WordPress shortcode, **[whatever-o-meter]**, or Hugo
shortcode **{{< whatever-o-meter >}}** to place the whatever-o-meter
on the page. Only one shortcode should appear an any one Wordpress or
Hugo page, further appearances will not work, although the meter dial
and intro text will appear.

The plugin uses Wordpress custom fields or Hugo front matter
parameters to define the questions, results and a number of optional
fields. The custom fields or parameters are:

* **intro** The initial text that will appear on the panel below the
  tacho dial and above the start button.
* **question** Each question has it's own entry, as many as required
  within reason. They will be asked in the order given.
* **left** Each text has it's own entry, as many as required. It will
  appear on the left below the slider. They will be displayed in the
  order given. There may be up to the same number of entries as
  questions. Optional, if not defined 'No' will appear
* **center**  Alternative spelling for them as can't spell.
* **centre** Each text has it's own entry, as many as required. It
  will appear in the centre below the slider. They will be displayed
  in the order given. There may be up to the same number of entries as
  questions. Optional, if not defined no centre text will appear. If
  an entry contains a single dash (-), no centre text will appear,
  allowing a centre text for following questions.
* **right** Each text has it's own entry, as many as required. It will
  appear on the right below the slider. They will be displayed in the
  order given. There may be up to the same number of entries as
  questions. Optional, if not defined 'Yes' will appear
* **result** Each result has it's own entry, as many as required. The
  results will be distributed equally around the tacho dial. If the
  result text contains %d%, the result percentage will be
  substituted. If five results are used, they will correspond roughly
  with the tacho dial segments.
* **weights** A comma delimited list of weighting values for the
  questions. If provided, there may be up to the same number of values
  as questions. Optional, if not provided the weighting value for
  questions will default to 1.
* **duration** The duration of the animation in
  milliseconds. Optional, defaults to 2000. See
  [JQuery](http://api.jquery.com/animate) docs.
* **easing** The easing function to be used for the dynamics of the
  tacho dial pointer. Optional, defaults to 'easeOutQuad'. See
  [JQuery UI](http://api.jqueryui.com/easings) docs.
* **more** Optional, if this field is defined a Find Out More button
  will appear on the results panel. The field should contain a valid
  URL.
* **fb-appid** Optional, if this field is defined a Facebook button
  will appear on the results panel which will show a Facebook feed
  dialog if clicked. The id must relate to an app defined on the
  [Facebook App Dashboard](https://developers.facebook.com/apps) for
  your site.
* **fb-caption** Optional, the caption you want to appear on the feed
  dialog. If not defined this will default to the page title.
* **fb-description** Optional, the description you want to appear in
  the feed dialog. If not defined, this will default to the result
  text. If the description contains %d%, the result percentage will be
  substituted. If the description contains %s, the whole result text
  will be substituted.
* **fb-picture** Optional, the picture you want to appear in the feed
  dialog. If not defined, Facebook will substitute an image from your
  site.
* **fb-like** Optional, if this is set to above standard Facebook like
  and share buttons will appear above the whatever-o-meter. If it is
  set to below, the buttons will appear below. The like and share
  buttons are a standard Facebook plugin and will not use information
  from the fields above.
* **colors** Alternative spelling for them as can't spell.
* **colours** The colours you would like to appear in the dial and
  buttons. Optional, should be a comma delimited list of five
  colours. The colours are the dial background colour, ticks, digits,
  pointer, buttons, any colour format in the CSS standard should work:
  #abc, #abcdef, goldenrod, rgb(r,g,b). Defaults to palegoldenrod,
  black, black, black, palegoldenrod.
* **debug** Causes the plugin to show the values of the custom fields
  below the whatever-o-meter for debugging if defined.

### Hugo
In the Hugo version parameters with a single value are defined as just
one item, parameters with multiple values are shown as an array.

```yaml
intro: Please answer the following questions carefully and truthfully.
question:
  - You are lying in bed on Monday morning...
weights: 2,1,1,1,1
```

The facebook and debug functionality is not implemented in Hugo.
