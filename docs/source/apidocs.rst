Endpoints
-----------

API list
+++++++++++++


.. envvar:: /ajax/getDistinct/<entry>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * ``entry`` (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/similarDistinct/<keyword>

    This is designed for the search bar on the website. It predicts what a user may be looking for based on where the dev specifies to search.

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl /ajax/similarDistinct/<keyword>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * ``keyword`` (string): ``user search query``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    This is a rest-like API that gives information about queried experiments from the e3smexp table.

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    **Example response**:

    .. sourcecode:: text

        list of experiments

    **Query parameters**
            * ``<searchTerms>`` (string): string value
            * ``<mlimit>`` (int): integer limit value
            * ``<orderBy>`` (string): value from the list ``["expid","total_pes_active","run_length","model_throughput","mpi_tasks_per_node","init_time","run_time","user","machine","compset","exp_date","res","e3smexp.case","case_group","lid"]``
            * ``<ascDsc>`` (string): value from the list ``['desc','asc']``

    .. note::

       note
        
.. envvar:: /ajax/specificSearch/<query>/<whitelist>

    This function is used by the scatter plot and sends requests of the form https://pace.ornl.gov/ajax/specificSearch/*/expid,machine,model_throughput,total_pes_active

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/specificSearch/*/expid,machine,model_throughput,total_pes_active

    **Example response**:

    .. sourcecode:: text

        returns scatter plot data

    **Query parameters**
            * query (string): string value
            * whitelist (string): value from the list ``[expid,machine,model_throughput,total_pes_active]``

    .. note::

       note

.. envvar:: /atmos/<expids>/

    Atmosphere model component stats page and also compare multiple experiments on atm

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/atmos/<expids>/

    **Example response**:

    .. tabs::

        .. tab:: Single experiment
            .. sourcecode:: json

                {
                    "ATM Other":{
                        "label":"ATM Other",
                        "name":"ATM Other",
                        "time":29.466,
                        "time_percentage":0.06
                    },
                    "a:crm_physics_tend":{
                        "label":"MMF",
                        "name":"a:crm_physics_tend",
                        "time":0,
                        "time_percentage":0
                    },
                    "a:macrop_tend":{
                        "label":"Macrophys",
                        "name":"a:macrop_tend",
                        "time":6562.556,
                        "time_percentage":12.83
                    },
                    "a:microp_tend":{
                        "label":"Microphys",
                        "name":"a:microp_tend",
                        "time":6033.725,
                        "time_percentage":11.8
                    },
                    "a:moist_convection":{
                        "label":"Convection",
                        "name":"a:moist_convection",
                        "time":1044.003,
                        "time_percentage":2.04
                    },
                    "a:phys_run2":{
                        "label":"Phys Aft Surface",
                        "name":"a:phys_run2",
                        "time":5313.299,
                        "time_percentage":10.39
                    },
                    "a:radiation":{
                        "label":"Radiation",
                        "name":"a:radiation",
                        "time":5968.201,
                        "time_percentage":11.67
                    },
                    "a:stepon_run1":{
                        "label":"Phys/Dyn Coupling",
                        "name":"a:stepon_run1",
                        "time":4874.382,
                        "time_percentage":9.53
                    },
                    "a:stepon_run3":{
                        "label":"Dynamics",
                        "name":"a:stepon_run3",
                        "time":10728.853,
                        "time_percentage":20.97
                    },
                    "a:tphysbc_aerosols":{
                        "label":"Aerosol",
                        "name":"a:tphysbc_aerosols",
                        "time":9559.003999999999,
                        "time_percentage":18.69
                    },
                    "a:wshist":{
                        "label":"Hist",
                        "name":"a:wshist",
                        "time":1038.471,
                        "time_percentage":2.03
                    }
                }

        .. tab:: Multiple experiment
            .. sourcecode:: json

                {
                    "Dyn":{
                        "time":[
                            0,
                            0,
                            0,
                            0
                        ],
                        "time_percentage":[
                            0,
                            0,
                            0,
                            0
                        ]
                    },
                    "SHOC":{
                        "time":[
                            0,
                            0,
                            0,
                            0
                        ],
                        "time_percentage":[
                            0,
                            0,
                            0,
                            0
                        ]
                    },
                    "SPA":{
                        "time":[
                            0,
                            0,
                            0,
                            0
                        ],
                        "time_percentage":[
                            0,
                            0,
                            0,
                            0
                        ]
                    },
                    "P3":{
                        "time":[
                            0,
                            0,
                            0,
                            0
                        ],
                        "time_percentage":[
                            0,
                            0,
                            0,
                            0
                        ]
                    },
                    "RRTMGPxx":{
                        "time":[
                            0,
                            0,
                            0,
                            0
                        ],
                        "time_percentage":[
                            0,
                            0,
                            0,
                            0
                        ]
                    },
                    "ATM Other":{
                        "time":[
                            38.675,
                            0,
                            0,
                            579.208
                        ],
                        "time_percentage":[
                            3.92,
                            0.0,
                            0.0,
                            100.0
                        ]
                    },
                    "Convection":{
                        "time":[
                            0,
                            224.679,
                            0,
                            0
                        ],
                        "time_percentage":[
                            0,
                            2.06,
                            0.0,
                            0.0
                        ]
                    },
                    "CLUBB":{
                        "time":[
                            108.379,
                            1882.563,
                            0,
                            0
                        ],
                        "time_percentage":[
                            10.99,
                            17.29,
                            0.0,
                            0.0
                        ]
                    },
                    "Aerosol":{
                        "time":[
                            81.688,
                            997.623,
                            0,
                            0
                        ],
                        "time_percentage":[
                            8.28,
                            9.16,
                            0.0,
                            0.0
                        ]
                    },
                    "Microphys":{
                        "time":[
                            269.573,
                            695.908,
                            0,
                            0
                        ],
                        "time_percentage":[
                            27.33,
                            6.39,
                            0.0,
                            0.0
                        ]
                    },
                    "Radiation":{
                        "time":[
                            449.087,
                            519.194,
                            0,
                            0
                        ],
                        "time_percentage":[
                            45.52,
                            4.77,
                            0.0,
                            0.0
                        ]
                    },
                    "Phys Aft Surface":{
                        "time":[
                            0,
                            2111.118,
                            0,
                            0
                        ],
                        "time_percentage":[
                            0,
                            19.39,
                            0.0,
                            0.0
                        ]
                    },
                    "Dynamics":{
                        "time":[
                            39.086,
                            2443.905,
                            0,
                            0
                        ],
                        "time_percentage":[
                            3.96,
                            22.44,
                            0.0,
                            0.0
                        ]
                    },
                    "Phys/Dyn Coupling":{
                        "time":[
                            0,
                            1767.0120000000002,
                            0,
                            0
                        ],
                        "time_percentage":[
                            0,
                            16.23,
                            0.0,
                            0.0
                        ]
                    },
                    "Hist":{
                        "time":[
                            0,
                            246.688,
                            0,
                            0
                        ],
                        "time_percentage":[
                            0,
                            2.27,
                            0.0,
                            0.0
                        ]
                    }
                }
   
    **Query parameters**
            * ``<expids>``: list of integer

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note

.. envvar:: /ajax/search/<searchTerms>/<int:mlimit>/<orderBy>/<ascDsc>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/getDistinct/<entry>

    **Example response**:

    .. sourcecode:: json

        [
            'summit',
            'cori',
            'compy'
        ]

    **Query parameters**
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note
