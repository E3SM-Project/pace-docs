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
    
    **Example response**:

    .. sourcecode:: json
        
        {
            "modelio":{
                "diri":"/compyfs/kezi456/E3SM_simulations/v2.master.mam5.PD/build/atm",
                "diro":"/compyfs/kezi456/E3SM_simulations/v2.master.mam5.PD/tests/S_1x5_ndays/run",
                "logfile":"atm.log.303313.220628-152730"
            },
            "pio_inparm":{
                "pio_netcdf_format":"64bit_offset",
                "pio_numiotasks":-99,
                "pio_rearranger":1,
                "pio_root":0,
                "pio_stride":40,
                "pio_typename":"pnetcdf"
            }
        }


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
    
    **Example response**:

    .. sourcecode:: json

        {
            "nodes":10,
            "total_tasks":400,
            "tasks_per_node":40,
            "thread_count":1,
            "ngpus_per_node":0,
            "env":{
                "I_MPI_ADJUST_ALLREDUCE":"1",
                "LD_LIBRARY_PATH":"/share/apps/gcc/8.1.0/lib:/share/apps/gcc/8.1.0/lib64:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/tbb/lib/intel64_lin/gcc4.7:/share/apps/pnetcdf/1.9.0/intel/19.0.5/intelmpi/2019u4/lib:/share/apps/netcdf/4.6.3/intel/19.0.5/lib:/share/apps/hdf5/1.10.5/serial/lib:/share/apps/intel/2019u4/compilers_and_libraries_2019.4.243/linux/mpi/intel64/libfabric/lib:/share/apps/intel/2019u4/compilers_and_libraries_2019.4.243/linux/mpi/intel64/lib/release:/share/apps/intel/2019u4/compilers_and_libraries_2019.4.243/linux/mpi/intel64/lib:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/compiler/lib/intel64_lin:/share/apps/intel/2019u5/comepilers_and_libraries_2019.5.281/linux/mpi/intel64/libfabric/lib:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/mpi/intel64/lib/release:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/mpi/intel64/lib:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/ipp/lib/intel64:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/compiler/lib/intel64_lin:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/mkl/lib/intel64_lin:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/tbb/lib/intel64/gcc4.7:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/tbb/lib/intel64/gcc4.7:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/daal/lib/intel64_lin:/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/daal/../tbb/lib/intel64_lin/gcc4.4",
                "MKL_PATH":"/share/apps/intel/2019u5/compilers_and_libraries_2019.5.281/linux/mkl",
                "NETCDF_HOME":"/share/apps/netcdf/4.6.3/intel/19.0.5/",
                "OMP_NUM_THREADS":"1"
            },
            "submit_cmd":"sbatch --time 00:20:00 -p short --account e3sm .case.run --resubmit",
            "mpirun":"srun --mpi=pmi2 --ntasks=400 --nodes=10 --kill-on-bad-exit -l --cpu_bind=cores -c 1 -m plane=40 /compyfs/kezi456/E3SM_simulations/v2.master.mam5.PD/build/e3sm.exe   >> e3sm.log.$LID 2>&1",
            "omp_threads":"1"
        }

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
    
    **Example response**:

    .. sourcecode:: json

        {
            "atm2ice_fmapname":"/lcrc/group/e3sm/data/inputdata/cpl/gridmaps/ne30pg2/map_ne30pg2_to_EC30to60E2r2_mono.201005.nc",
            "atm2ice_fmaptype":"X",
            "atm2ice_smapname":"/lcrc/group/e3sm/data/inputdata/cpl/gridmaps/ne30pg2/map_ne30pg2_to_EC30to60E2r2_bilin.201005.nc",
            "atm2ice_smaptype":"X",
            "atm2ice_vmapname":"/lcrc/group/e3sm/data/inputdata/cpl/gridmaps/ne30pg2/map_ne30pg2_to_EC30to60E2r2_bilin.201005.nc",
            "atm2ice_vmaptype":"X",
            "atm2lnd_fmapname":"idmap",
            "atm2lnd_fmaptype":"X",
            "atm2lnd_smapname":"idmap",
            "atm2lnd_smaptype":"X",
            "atm2ocn_fmapname":"/lcrc/group/e3sm/data/inputdata/cpl/gridmaps/ne30pg2/map_ne30pg2_to_EC30to60E2r2_mono.201005.nc",
            "atm2ocn_fmaptype":"X"
        }

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
    
    **Example response**:

    .. sourcecode:: json

        {
            "name":"create_newcase",
            "date":"2021-06-07 10:17:07",
            "case":"/global/cscratch1/sd/blazg/e3sm_scratch/e3sm_v1.2_ne30_noAgg-60",
            "mach":"cori-knl",
            "res":"ne30_ne30",
            "compset":"F2010",
            "compiler":"intel"
        }

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
    
    **Example response**:

    .. sourcecode:: json

        [
            {
                "data":"...text...",
                "name":"EAM-410856",
                "iopercent":65.15,
                "iotime":231.45,
                "version":"1.0.0"
            }
        ]

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
    
    **Example response**:

    .. sourcecode:: json

        {
            "file":{
                "@id":"env_batch.xml",
                "@version":"2.0",
                "header":"These variables may be changed anytime during a run, they\n      control arguments to the batch submit command.",
                "group":[
                    {
                        "@id":"config_batch",
                        "entry":{
                        "@id":"BATCH_SYSTEM",
                        "@value":"slurm",
                        "type":"char",
                        "valid_values":"nersc_slurm,lc_slurm,moab,pbs,lsf,slurm,cobalt,cobalt_theta,none",
                        "desc":"The batch system type to use for this machine."
                        }
                    },
                    {
                        "@id":"job_submission",
                        "entry":{
                        "@id":"PROJECT_REQUIRED",
                        "@value":"FALSE",
                        "type":"logical",
                        "valid_values":"TRUE,FALSE",
                        "desc":"whether the PROJECT value is required on this machine"
                        }
                    }
                ],
                "batch_system":[
                    {
                        "@type":"slurm",
                        "batch_query":{
                        "@per_job_arg":"-j",
                        "#text":"squeue"
                        },
                        "batch_submit":"sbatch",
                        "batch_cancel":"scancel",
                        "batch_directive":"#SBATCH",
                        "jobid_pattern":"(\\d+)$",
                        "depend_string":"--dependency=afterok:jobid",
                        "depend_allow_string":"--dependency=afterany:jobid",
                        "depend_separator":":",
                        "walltime_format":"%H:%M:%S",
                        "batch_mail_flag":"--mail-user",
                        "batch_mail_type_flag":"--mail-type",
                        "batch_mail_type":"none, all, begin, end, fail",
                        "submit_args":{
                        "arg":[
                            {
                                "@flag":"--time",
                                "@name":"$JOB_WALLCLOCK_TIME"
                            },
                            {
                                "@flag":"-p",
                                "@name":"$JOB_QUEUE"
                            },
                            {
                                "@flag":"--account",
                                "@name":"$PROJECT"
                            }
                        ]
                        },
                        "directives":{
                        "directive":[
                            "--job-name={{ job_id }}",
                            "--nodes={{ num_nodes }}",
                            "--output={{ job_id }}.%j",
                            "--exclusive"
                        ]
                        }
                    },
                    {
                        "@MACH":"chrysalis",
                        "@type":"slurm",
                        "directives":{
                        "directive":"--switches=$SHELL{echo \"(`./xmlquery --value NUM_NODES` + 19) / 20\" |bc}"
                        },
                        "queues":{
                        "queue":[
                            {
                                "@walltimemax":"48:00:00",
                                "@strict":"true",
                                "@nodemin":"1",
                                "@nodemax":"492",
                                "#text":"compute"
                            },
                            {
                                "@walltimemax":"04:00:00",
                                "@strict":"true",
                                "@nodemin":"1",
                                "@nodemax":"20",
                                "@default":"true",
                                "#text":"debug"
                            }
                        ]
                        }
                    }
                ]
            }
        }

    .. note::

        data is json object


Unit Test Parser
-----------------

    To perform unit test for e3sm parsers, use e3smParserTest.py script available under pace/e3sm/unit_test

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            python3 e3smParserTest.py
    
    **Example response**:

    .. sourcecode:: bash

        ............
        ----------------------------------------------------------------------
        Ran 12 tests in 0.017s

        OK

    .. note::

        Test case are pre-defined
        