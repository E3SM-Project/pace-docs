Endpoints
-----------

API list
+++++++++++++


.. envvar:: /ajax/getDistinct/<entry>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl -H "Authorization: Token <token>" https://readthedocs.org/api/v3/projects/

        .. code-tab:: python

            import requests

    **Example response**:

    .. sourcecode:: json

        {
            "count": 25,
            "next": "/api/v3/projects/?limit=10&offset=10",
            "previous": null
        }

    :>json string next: URI for next set of Projects.
    :>json string previous: URI for previous set of Projects.
    :>json integer count: Total number of Projects.
    :>json array results: Array of ``Project`` objects.

    :query string slug: Narrow the results by matching the exact project slug
    
    .. note::

       note