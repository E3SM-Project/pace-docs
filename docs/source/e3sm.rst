E3SM
==============


Parser
--------------


Build Time
++++++++++++++

    This parses file build_times.txt.

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseBuildTime

            data, total_compute_cost, total_elasped_time = parseBuildTime.loaddb_buildTimesFile(filename)
    
    .. note::

        data consist of long string
        total_compute_cost, total_elasped_time are floating numbers

Timing
++++++++++++++

    This parses file e3sm_timing.* file.

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseE3SMTiming

            successFlag, timingProfileInfo, componentTable, runTimeTable = parseE3SMTiming.parseE3SMtiming(filename)
    
    .. note::

        successFlag is bolean
        timingProfileInfo is json object
        componentTable, runTimeTable are list

Memory Profile
++++++++++++++

    This parses file memory.* .

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseMemoryProfile

            data = parseMemoryProfile.loaddb_memfile(filename)
    
    .. note::

        data is long string

Model Version
++++++++++++++

    This parses file GIT_DESCRIBE.* .

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseModelVersion

            data = parseModelVersion.parseModelVersion(filename)
    
    .. note::

        data is string

Namelist
++++++++++++++

    This parses file namelist files in casedocs.

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseNameList

            data = parseNameList.loaddb_namelist(file)
    
    .. note::

        data is json object

Preview Run
++++++++++++++

    This parses file preview_run.log.* .
    
    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parsePreviewRun

            data = parsePreviewRun.load_previewRunFile(file)
    
    .. note::

        data is json object

RC File
++++++++++++++

    This parses file seq_maps.rc.* .

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseRC

            data = parseRC.loaddb_rcfile(file)
    
    .. note::

        data is json object

README File
++++++++++++++

    This parses file README.case.* .

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseReadMe

            data = parseReadMe.parseReadme(file)
    
    .. note::

        data is a json object

Replay sh
++++++++++++++

    This parses file replay.sh.* .

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseReplaysh

            data = parseReplaysh.load_replayshFile(file)
    
    .. note::

        data is a text blob

Run e3sm sh
++++++++++++++

    This parses file run_e3sm.sh.* .

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseRunE3SMsh

            data = parseRunE3SMsh.load_rune3smshfile(file)
    
    .. note::

        data is text blob

Scorpio
++++++++++++++

    This parses file scorpio_stats.* .

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseScorpioStats
            
            run_time = 5 #(actual experiment run_time)
            data = parseScorpioStats.loaddb_scorpio_stats(file,run_time)
    
    .. note::

        data is a list of json.

XML File
++++++++++++++

    This parses XML files in casedocs.

    **Example request**:

    .. tabs::

        .. code-tab:: python

            import parseXML

            data = parseXML.loaddb_xmlfile(file)
    
    .. note::

        data is json object

