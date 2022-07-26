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
            * entry (string): value from the list ``['machine,'user']``

    .. note::

       note