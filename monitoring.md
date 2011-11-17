---
title: "RQ: Simple job queues for Python"
layout: default
---

<div class="warning">
    <img style="float: right; margin-right: -60px; margin-top: 38px; height: 100px;" src="http://a.dryicons.com/images/icon_sets/colorful_stickers_icons_set/png/256x256/warning.png" />
    <strong>Be warned!</strong>
    <p>The stuff below does not exist yet!</p>
    <p>I merely use this page to daydream about features and to do some document-driven design.</p>
</div>

Monitoring is where RQ shines.


## Seeing what queues exist

To see what queues exist (and how many jobs there are to process them):

{% highlight console %}
$ rqinfo --queues
high
low
normal
default
4 queues
{% endhighlight %}


{% highlight console %}
$ rqinfo --queues
high         20 |██████████████████████████
low          12 |██████████████
normal        8 |█████████
default       0 |
4 queues, 45 jobs total
{% endhighlight %}


## Seeing active workers

To see what workers are currently active:

{% highlight console %}
$ rqinfo --workers
worker          queues            jobs   state
--------------- ----------------- ------ --------
mickey.27939    high,normal,low   34     busy
mickey.8239     high,normal,low   120    busy
turkish.32682   high              200    idle
bricktop.2682   weekly            1      starting
foobar.2658     default           1      idle
4 workers listening on 4 queues
{% endhighlight %}


{% highlight console %}
$ rqinfo --workers --verbose
worker          queues            jobs   since      state
--------------- ----------------- ------ ---------- --------
mickey.27939    high,normal,low   34     4d 11h 6m  busy
mickey.8239     high,normal,low   120    21d 2h 4m  busy
turkish.32682   high              200    1h 7m 3s   idle
bricktop.2682   weekly            1      1m 7s      starting
foobar.2658     default           1      1m 7s      idle
4 workers listening on 4 queues
{% endhighlight %}

