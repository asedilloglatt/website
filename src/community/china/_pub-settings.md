
{% assign id =  include.os | downcase -%}

<div id="{{id}}-pub" class="tab-pane
  {%- if id == 'windows' %} active {% endif %}"
  role="tabpanel" aria-labelledby="{{id}}-tab" markdown="1">

1. Configure a proxy.
   To configure a proxy, check out the [Dart documentation on proxies][].

  {% comment %}
  From https://github.com/flutter/website/issues/2556#issuecomment-481566476
  {% endcomment %}

1. Verify that your `PUB_HOSTED_URL` environment variable is either unset
   or empty.

   {% if id == 'windows' -%}

   ```terminal
   {{prompt}} echo $env:PUB_HOSTED_URL
   ```

   If this command returns any value, unset it.

   ```terminal
   {{prompt}} Remove-Item $env:PUB_HOSTED_URL
   ```

   {% else -%}

   ```terminal
   {{prompt}} echo $PUB_HOSTED_URL
   ```

   If this command returns any value, unset it.

   ```terminal
   {{prompt}} unset $PUB_HOSTED_URL
   ```

   {% endif %}

</div>
