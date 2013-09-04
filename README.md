# Cluster events

You can bind events to clusters the same way as markers. For all the events availble see the google maps api https://developers.google.com/maps/documentation/javascript/reference#Marker

```
$('#map').gmap3({
  marker:{
    values: list,
    cluster:{
      radius: 40, 
      // This style will be used for clusters with more than 0 markers
      0: {
        content: '<div class="cluster cluster-1">CLUSTER_COUNT</div>',
        width: 53,
        height: 52
      },
      events: {
        click: clickOnCluster,
        rightclick: function(overlay, event, context){ doSomething }
      }
    }
  }
});
```

The argument `context` contains the latLng of the cluster inside `context.data.latLng` and the markers inside the cluster `context.data.markers`

This is the only way I've found that gets what markers are inside a cluster.  What I would like is to be able to have a callback when the cluster is styled/created so that I can customise the clusters appearance depending on what markers are inside.

Code is an extended demo from https://github.com/jbdemonte/gmap3