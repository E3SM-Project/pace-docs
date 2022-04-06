Compare Multiple Experiments
=======

After checking the box for your desired experiments.
Available graphs are flame, tree and atmosphere component.
Available graphs buttons will light up green.

.. image:: pictures/HomeScreenMultipleCompare.png


Flame graph
------------

Looking at how time is distributed on various application ridges. Flame graph helps to view the row of various processes time distribution.
The time process can be navigeted further deeper by clicking on the process time bar in flame graph.

.. image:: pictures/flameGraphMultiple.png


Tree graph
------------

Tree graph shows the time distributed for each componenent of process time as a bar chart.

.. image:: pictures/treeGraphMultiple.png

Atmosphere componenet graph
----------------

This graph shows the time distribution of the atmosphere component process. Following process time are displayed in the graph
To view for specific experiments, click on labels on top of graph which will hide/show that data point.
Use labels to filter further down to your interest.

.. table::

+-------------------+-------------------------------------------+
| Label             | Timer(s)                                  |
+===================+===========================================+
| Convention        | 'a:moist_convection'                      |
+-------------------+-------------------------------------------+
| CLUBB             | 'a:macrop_tend'                           |
+-------------------+-------------------------------------------+
| Aerosol           | 'a:microp_aero_run' + 'a:tphysbc_aerosols'|
+-------------------+-------------------------------------------+
| Microphys         | 'a:microp_tend'                           |
+-------------------+-------------------------------------------+
| Radiation         | 'a:radiation'                             |
+-------------------+-------------------------------------------+
| Phys aft surface  | 'a:phys_runs2'                            |
+-------------------+-------------------------------------------+
| Dynamics          | 'a:stepon_run3'                           |
+-------------------+-------------------------------------------+
| Phys/Dyn Coupling | 'a:stepon_run1' + 'a:stepon_run2'         |
+-------------------+-------------------------------------------+
| Hist              | 'a:wshist'                                |
+-------------------+-------------------------------------------+
| ATM Other         | 'CPL:ATM_RUN' - sun (all above timers)    |
+-------------------+-------------------------------------------+


.. image:: pictures/atmGraphMultiple.png
    



