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

    .. sourcecode:: text

        predicts what a user may be looking for 

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

    This function is used by the scatter plot and sends requests of the form ``https://pace.ornl.gov/ajax/specificSearch/*/expid,machine,model_throughput,total_pes_active``

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/ajax/specificSearch/*/expid,machine,model_throughput,total_pes_active

    **Example response**:

    .. sourcecode:: text

        returns scatter plot data

    **Query parameters**
            * ``query (string)``: string value
            * ``whitelist (string)``: value from the list ``[expid,machine,model_throughput,total_pes_active]``

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

.. envvar:: /benchmarks/<keyword>

    get list of benchmarks

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/benchmarks/<keyword>

    **Example response**:

    .. sourcecode:: json

        [
            'High-res Atmosphere',
            'High-res Ocean'
        ]

    **Query parameters**
            * ``keyword`` (string): value in the list of ``["FC5AV1C-H01A", "GMPAS-IAF"]``

    .. note::

       note

.. envvar:: /buildtime/<int:mexpid>

    This api is to get the build time stats page

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/buildtime/<int:mexpid>

    **Example response**:

    .. sourcecode:: json

        [
            {
                "name":"CMakeFiles/rof.dir/__/__/mosart/src/cpl/rof_comp_esmf.F90.o",
                "time":0.172597
            },
            {
                "name":"CMakeFiles/wav.dir/__/__/stub_comps/swav/src/wav_comp_mct.F90.o",
                "time":0.284152
            },
            {
                "name":"CMakeFiles/glc.dir/__/__/stub_comps/sglc/src/glc_comp_mct.F90.o",
                "time":0.294248
            },
            {
                "name":"CMakeFiles/rof.dir/__/__/mosart/src/riverroute/RtmSpmd.F90.o",
                "time":0.177503
            },
            {
                "name":"libwav.a",
                "time":0.032712
            }
        ]

    **Query parameters**
            * ``mexpid (int)``: experiment id value

    .. note::

       note

.. envvar:: /e3smrunsh/<int:mexpid>

    e3sm_run sh script page

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/e3smrunsh/<int:mexpid>

    **Example response**:

    .. sourcecode:: bash

        #!/bin/bash -fe

        # E3SM Water Cycle v2 run_e3sm script template.
        #
        # Inspired by v1 run_e3sm script as well as SCREAM group simplified run script.
        #
        # Bash coding style inspired by:
        # http://kfirlavi.herokuapp.com/blog/2012/11/14/defensive-bash-programming

        # TO DO:
        # - custom pelayout

        main() {

        # For debugging, uncomment line below
        #set -x

        # --- Configuration flags ----

        # Machine and project
        readonly MACHINE=anvil
        readonly PROJECT="condo"

        # Simulation
        readonly COMPSET="S"
        readonly RESOLUTION="f19_g16"
        # BEFORE RUNNING : CHANGE the following CASE_NAME to desired value
        readonly CASE_NAME="test_perf_archive"
        # If this is part of a simulation campaign, ask your group lead about using a case_group label
        # readonly CASE_GROUP=""

        # Code and compilation
        readonly CHECKOUT="20210806"
        readonly BRANCH="master"
        readonly CHERRY=( )
        readonly DEBUG_COMPILE=false

        # Run options
        readonly MODEL_START_TYPE="hybrid"  # 'initial', 'continue', 'branch', 'hybrid'
        readonly START_DATE="0001-01-01"

        # Additional options for 'branch' and 'hybrid'
        readonly GET_REFCASE=FALSE
        readonly RUN_REFDIR="/global/cscratch1/sd/forsyth/E3SMv2/v2.LR.piControl/init"
        readonly RUN_REFCASE="20210625.v2rc3c-GWD.piControl.ne30pg2_EC30to60E2r2.chrysalis"
        readonly RUN_REFDATE="1001-01-01"   # same as MODEL_START_DATE for 'branch', can be different for 'hybrid'

        # Set paths
        readonly CODE_ROOT="/home/ac.boutte3/E3SM"
        readonly CASE_ROOT="/lcrc/group/e3sm/ac.boutte3/scratch/anvil/${CASE_NAME}"

        # Sub-directories
        readonly CASE_BUILD_DIR=${CASE_ROOT}/build
        readonly CASE_ARCHIVE_DIR=${CASE_ROOT}/archive

        # Define type of run
        #  short tests: 'XS_2x5_ndays', 'XS_1x10_ndays', 'S_1x10_ndays',
        #               'M_1x10_ndays', 'M2_1x10_ndays', 'M80_1x10_ndays', 'L_1x10_ndays'
        #  or 'production' for full simulation
        readonly run='XS_2x5_ndays'
        if [ "${run}" != "production" ]; then

        # Short test simulations
        tmp=($(echo $run | tr "_" " "))
        layout=${tmp[0]}
        units=${tmp[2]}
        resubmit=$(( ${tmp[1]%%x*} -1 ))
        length=${tmp[1]##*x}

        readonly CASE_SCRIPTS_DIR=${CASE_ROOT}/tests/${run}/case_scripts
        readonly CASE_RUN_DIR=${CASE_ROOT}/tests/${run}/run
        readonly PELAYOUT=${layout}
        readonly WALLTIME="2:00:00"
        readonly STOP_OPTION=${units}
        readonly STOP_N=${length}
        readonly REST_OPTION=${STOP_OPTION}
        readonly REST_N=${STOP_N}
        readonly RESUBMIT=${resubmit}
        readonly DO_SHORT_TERM_ARCHIVING=false

        else

        # Production simulation
        readonly CASE_SCRIPTS_DIR=${CASE_ROOT}/case_scripts
        readonly CASE_RUN_DIR=${CASE_ROOT}/run
        readonly PELAYOUT="L"
        readonly WALLTIME="34:00:00"
        readonly STOP_OPTION="nyears"
        readonly STOP_N="50"
        readonly REST_OPTION="nyears"
        readonly REST_N="5"
        readonly RESUBMIT="9"
        readonly DO_SHORT_TERM_ARCHIVING=false
        fi

        # Coupler history
        readonly HIST_OPTION="nyears"
        readonly HIST_N="5"

        # Leave empty (unless you understand what it does)
        readonly OLD_EXECUTABLE=""

        # --- Toggle flags for what to do ----
        do_fetch_code=false
        do_create_newcase=true
        do_case_setup=true
        do_case_build=true
        do_case_submit=true

        # --- Now, do the work ---

        # Make directories created by this script world-readable
        umask 022

        # Fetch code from Github
        fetch_code

        # Create case
        create_newcase

        # Setup
        case_setup

        # Build
        case_build

        # Configure runtime options
        runtime_options

        # Copy script into case_script directory for provenance
        copy_script

        # Submit
        case_submit

        # All done
        echo $'\n----- All done -----\n'

        }

        # =======================
        # Custom user_nl settings
        # =======================

        user_nl() {

        cat << EOF >> user_nl_eam
        nhtfrq =   0,-24,-6,-6,-3,-24,0
        mfilt  = 1,30,120,120,240,30,1
        avgflag_pertape = 'A','A','I','A','A','A','I'
        fexcl1 = 'CFAD_SR532_CAL', 'LINOZ_DO3', 'LINOZ_DO3_PSC', 'LINOZ_O3CLIM', 'LINOZ_O3COL', 'LINOZ_SSO3', 'hstobie_linoz'
        fincl1 = 'extinct_sw_inp','extinct_lw_bnd7','extinct_lw_inp','CLD_CAL', 'TREFMNAV', 'TREFMXAV'
        fincl2 = 'FLUT','PRECT','U200','V200','U850','V850','Z500','OMEGA500','UBOT','VBOT','TREFHT','TREFHTMN:M','TREFHTMX:X','QREFHT','TS','PS','TMQ','TUQ','TVQ','TOZ', 'FLDS', 'FLNS', 'FSDS', 'FSNS', 'SHFLX', 'LHFLX', 'TGCLDCWP', 'TGCLDIWP', 'TGCLDLWP', 'CLDTOT', 'T250', 'T200', 'T150', 'T100', 'T050', 'T025', 'T010', 'T005', 'T002', 'T001', 'TTOP', 'U250', 'U150', 'U100', 'U050', 'U025', 'U010', 'U005', 'U002', 'U001', 'UTOP', 'FSNT', 'FLNT'
        fincl3 = 'PSL','T200','T500','U850','V850','UBOT','VBOT','TREFHT', 'Z700', 'TBOT:M'
        fincl4 = 'FLUT','U200','U850','PRECT','OMEGA500'
        fincl5 = 'PRECT','PRECC','TUQ','TVQ','QFLX','SHFLX','U90M','V90M'
        fincl6 = 'CLDTOT_ISCCP','MEANCLDALB_ISCCP','MEANTAU_ISCCP','MEANPTOP_ISCCP','MEANTB_ISCCP','CLDTOT_CAL','CLDTOT_CAL_LIQ','CLDTOT_CAL_ICE','CLDTOT_CAL_UN','CLDHGH_CAL','CLDHGH_CAL_LIQ','CLDHGH_CAL_ICE','CLDHGH_CAL_UN','CLDMED_CAL','CLDMED_CAL_LIQ','CLDMED_CAL_ICE','CLDMED_CAL_UN','CLDLOW_CAL','CLDLOW_CAL_LIQ','CLDLOW_CAL_ICE','CLDLOW_CAL_UN'
        fincl7 = 'O3', 'PS', 'TROP_P'

        ! Additional retuning
        clubb_tk1 = 268.15D0
        gw_convect_hcf = 10.0
        EOF

        cat << EOF >> user_nl_elm
        hist_dov2xy = .true.,.true.
        hist_fincl2 = 'H2OSNO', 'FSNO', 'QRUNOFF', 'QSNOMELT', 'FSNO_EFF', 'SNORDSL', 'SNOW', 'FSDS', 'FSR', 'FLDS', 'FIRE', 'FIRA'
        hist_mfilt = 1,365
        hist_nhtfrq = 0,-24
        hist_avgflag_pertape = 'A','A'
        EOF

        cat << EOF >> user_nl_mosart
        rtmhist_fincl2 = 'RIVER_DISCHARGE_OVER_LAND_LIQ'
        rtmhist_mfilt = 1,365
        rtmhist_ndens = 2
        rtmhist_nhtfrq = 0,-24
        EOF

        }

        patch_mpas_streams() {

        echo

        }

        ######################################################
        ### Most users won't need to change anything below ###
        ######################################################

        #-----------------------------------------------------
        fetch_code() {

            if [ "${do_fetch_code,,}" != "true" ]; then
                echo $'\n----- Skipping fetch_code -----\n'
                return
            fi

            echo $'\n----- Starting fetch_code -----\n'
            local path=${CODE_ROOT}
            local repo=e3sm

            echo "Cloning $repo repository branch $BRANCH under $path"
            if [ -d "${path}" ]; then
                echo "ERROR: Directory already exists. Not overwriting"
                exit 20
            fi
            mkdir -p ${path}
            pushd ${path}

            # This will put repository, with all code
            git clone git@github.com:E3SM-Project/${repo}.git .

            # Setup git hooks
            rm -rf .git/hooks
            git clone git@github.com:E3SM-Project/E3SM-Hooks.git .git/hooks
            git config commit.template .git/hooks/commit.template

            # Check out desired branch
            git checkout ${BRANCH}

            # Custom addition
            if [ "${CHERRY}" != "" ]; then
                echo ----- WARNING: adding git cherry-pick -----
                for commit in "${CHERRY[@]}"
                do
                    echo ${commit}
                    git cherry-pick ${commit}
                done
                echo -------------------------------------------
            fi

            # Bring in all submodule components
            git submodule update --init --recursive

            popd
        }

        #-----------------------------------------------------
        create_newcase() {

            if [ "${do_create_newcase,,}" != "true" ]; then
                echo $'\n----- Skipping create_newcase -----\n'
                return
            fi

            echo $'\n----- Starting create_newcase -----\n'

            if [[ -z "$CASE_GROUP" ]]; then
                ${CODE_ROOT}/cime/scripts/create_newcase \
                    --case ${CASE_NAME} \
                    --output-root ${CASE_ROOT} \
                    --script-root ${CASE_SCRIPTS_DIR} \
                    --handle-preexisting-dirs u \
                    --compset ${COMPSET} \
                    --res ${RESOLUTION} \
                    --machine ${MACHINE} \
                    --walltime ${WALLTIME} \
                    --pecount ${PELAYOUT}
            else
                ${CODE_ROOT}/cime/scripts/create_newcase \
                    --case ${CASE_NAME} \
                    --case-group ${CASE_GROUP} \
                    --output-root ${CASE_ROOT} \
                    --script-root ${CASE_SCRIPTS_DIR} \
                    --handle-preexisting-dirs u \
                    --compset ${COMPSET} \
                    --res ${RESOLUTION} \
                    --machine ${MACHINE} \
                    --walltime ${WALLTIME} \
                    --pecount ${PELAYOUT}
            fi
            

            if [ $? != 0 ]; then
            echo $'\nNote: if create_newcase failed because sub-directory already exists:'
            echo $'  * delete old case_script sub-directory'
            echo $'  * or set do_newcase=false\n'
            exit 35
            fi

        }

        #-----------------------------------------------------
        case_setup() {

            if [ "${do_case_setup,,}" != "true" ]; then
                echo $'\n----- Skipping case_setup -----\n'
                return
            fi

            echo $'\n----- Starting case_setup -----\n'
            pushd ${CASE_SCRIPTS_DIR}

            # Setup some CIME directories
            ./xmlchange EXEROOT=${CASE_BUILD_DIR}
            ./xmlchange RUNDIR=${CASE_RUN_DIR}

            # Short term archiving
            ./xmlchange DOUT_S=${DO_SHORT_TERM_ARCHIVING^^}
            ./xmlchange DOUT_S_ROOT=${CASE_ARCHIVE_DIR}

            # Build with COSP, except for a data atmosphere (datm)
            if [ `./xmlquery --value COMP_ATM` == "datm"  ]; then
            echo $'\nThe specified configuration uses a data atmosphere, so cannot activate COSP simulator\n'
            else
            echo $'\nConfiguring E3SM to use the COSP simulator\n'
            # ./xmlchange --id CAM_CONFIG_OPTS --append --val='-cosp'
            fi

            # Extracts input_data_dir in case it is needed for user edits to the namelist later
            local input_data_dir=`./xmlquery DIN_LOC_ROOT --value`

            # Custom user_nl
            user_nl

            # Finally, run CIME case.setup
            ./case.setup --reset

            popd
        }

        #-----------------------------------------------------
        case_build() {

            pushd ${CASE_SCRIPTS_DIR}

            # do_case_build = false
            if [ "${do_case_build,,}" != "true" ]; then

                echo $'\n----- case_build -----\n'

                if [ "${OLD_EXECUTABLE}" == "" ]; then
                    # Ues previously built executable, make sure it exists
                    if [ -x ${CASE_BUILD_DIR}/e3sm.exe ]; then
                        echo 'Skipping build because $do_case_build = '${do_case_build}
                    else
                        echo 'ERROR: $do_case_build = '${do_case_build}' but no executable exists for this case.'
                        exit 297
                    fi
                else
                    # If absolute pathname exists and is executable, reuse pre-exiting executable
                    if [ -x ${OLD_EXECUTABLE} ]; then
                        echo 'Using $OLD_EXECUTABLE = '${OLD_EXECUTABLE}
                        cp -fp ${OLD_EXECUTABLE} ${CASE_BUILD_DIR}/
                    else
                        echo 'ERROR: $OLD_EXECUTABLE = '$OLD_EXECUTABLE' does not exist or is not an executable file.'
                        exit 297
                    fi
                fi
                echo 'WARNING: Setting BUILD_COMPLETE = TRUE.  This is a little risky, but trusting the user.'
                ./xmlchange BUILD_COMPLETE=TRUE

            # do_case_build = true
            else

                echo $'\n----- Starting case_build -----\n'

                # Turn on debug compilation option if requested
                if [ "${DEBUG_COMPILE^^}" == "TRUE" ]; then
                    ./xmlchange DEBUG=${DEBUG_COMPILE^^}
                fi

                # Run CIME case.build
                ./case.build

                # Some user_nl settings won't be updated to *_in files under the run directory
                # Call preview_namelists to make sure *_in and user_nl files are consistent.
                ./preview_namelists

            fi

            popd
        }

        #-----------------------------------------------------
        runtime_options() {

            echo $'\n----- Starting runtime_options -----\n'
            pushd ${CASE_SCRIPTS_DIR}

            # Set simulation start date
            ./xmlchange RUN_STARTDATE=${START_DATE}

            # Segment length
            ./xmlchange STOP_OPTION=${STOP_OPTION,,},STOP_N=${STOP_N}

            # Restart frequency
            ./xmlchange REST_OPTION=${REST_OPTION,,},REST_N=${REST_N}

            # Coupler history
            ./xmlchange HIST_OPTION=${HIST_OPTION,,},HIST_N=${HIST_N}

            # Coupler budgets (always on)
            ./xmlchange BUDGETS=TRUE

            # Set resubmissions
            if (( RESUBMIT > 0 )); then
                ./xmlchange RESUBMIT=${RESUBMIT}
            fi

            # Run type
            # Start from default of user-specified initial conditions
            if [ "${MODEL_START_TYPE,,}" == "initial" ]; then
                ./xmlchange RUN_TYPE="startup"
                ./xmlchange CONTINUE_RUN="FALSE"

            # Continue existing run
            elif [ "${MODEL_START_TYPE,,}" == "continue" ]; then
                ./xmlchange CONTINUE_RUN="TRUE"

            elif [ "${MODEL_START_TYPE,,}" == "branch" ] || [ "${MODEL_START_TYPE,,}" == "hybrid" ]; then
                ./xmlchange RUN_TYPE=${MODEL_START_TYPE,,}
                ./xmlchange GET_REFCASE=${GET_REFCASE}
            ./xmlchange RUN_REFDIR=${RUN_REFDIR}
                ./xmlchange RUN_REFCASE=${RUN_REFCASE}
                ./xmlchange RUN_REFDATE=${RUN_REFDATE}
                echo 'Warning: $MODEL_START_TYPE = '${MODEL_START_TYPE}
            echo '$RUN_REFDIR = '${RUN_REFDIR}
            echo '$RUN_REFCASE = '${RUN_REFCASE}
            echo '$RUN_REFDATE = '${START_DATE}

            else
                echo 'ERROR: $MODEL_START_TYPE = '${MODEL_START_TYPE}' is unrecognized. Exiting.'
                exit 380
            fi

            # Patch mpas streams files
            patch_mpas_streams

            popd
        }

        #-----------------------------------------------------
        case_submit() {

            if [ "${do_case_submit,,}" != "true" ]; then
                echo $'\n----- Skipping case_submit -----\n'
                return
            fi

            echo $'\n----- Starting case_submit -----\n'
            pushd ${CASE_SCRIPTS_DIR}

            # Run CIME case.submit
            ./case.submit

            popd
        }

        #-----------------------------------------------------
        copy_script() {

            echo $'\n----- Saving run script for provenance -----\n'

            local script_provenance_dir=${CASE_SCRIPTS_DIR}/run_script_provenance
            mkdir -p ${script_provenance_dir}
            local this_script_name=`basename $0`
            local script_provenance_name=${this_script_name}.`date +%Y%m%d-%H%M%S`
            cp -vp ${this_script_name} ${script_provenance_dir}/${script_provenance_name}

        }

        #-----------------------------------------------------
        # Silent versions of popd and pushd
        pushd() {
            command pushd "$@" > /dev/null
        }
        popd() {
            command popd "$@" > /dev/null
        }

        # Now, actually run the script
        #-----------------------------------------------------
        main

    **Query parameters**
            * ``mexpid (int)``: experiment id value

    .. note::

       note

.. envvar:: /exp-details/<int:mexpid>

    experiment details stats page

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/exp-details/<int:mexpid>

    **Example response**:

    .. sourcecode:: text

        html page created for experiment details

    **Query parameters**
            * ``mexpid (int)``: experiment id value

    .. note::

       note

.. envvar:: /flamegraph/<expid>/<rank>/

    static page which provide flamegraph of the model timing

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/flamegraph/<expid>/<rank>/

    **Example response**:

    .. sourcecode:: text

        flamegraph.html template

    **Query parameters**
            * ``expid (int)``: experiment id value
            * ``rank (string)``: rank value of the experiment

    .. note::

       note

.. envvar:: /memoryprofile/<int:mexpid>

    Get memory profile stats page

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/memoryprofile/<int:mexpid>

    **Example response**:

    .. sourcecode:: text

        memoryProfilePage.html template

    **Query parameters**
            * ``mexpid (int)``: experiment id value

    .. note::

       note

.. envvar:: /nmlviewer/<int:mexpid>/<mname>

    Get nml view stats page

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/nmlviewer/<int:mexpid>/<mname>

    **Example response**:

    .. sourcecode:: text

        tabulator.html template

    **Query parameters**
            * ``mexpid (int)``: experiment id value
            * ``mname (string)``: namelist filename 

    .. note::

       note

.. envvar:: /note/<int:expID>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/note/<int:expID>

    **Example response**:

    .. sourcecode:: json

        note.html template

    **Query parameters**
            * ``expID (int)``: experiment id value

    .. note::

       note

.. envvar:: /platforms/<platform>/

    Get list of experiments for specific platforms

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/platforms/<platform>/

    **Example response**:

    .. sourcecode:: json

        list of experiments for specific machine

    **Query parameters**
            * ``platform (string)``: name of the machine

    .. note::

       note

.. envvar:: /rcviewer/<int:mexpid>/<mname>

    Get rc view stats page

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/rcviewer/<int:mexpid>/<mname>

    **Example response**:

    .. sourcecode:: json

        {
            "atm2ice_fmapname":"idmap",
            "atm2ice_fmaptype":"X",
            "atm2ice_smapname":"idmap",
            "atm2ice_smaptype":"X",
            "atm2ice_vmapname":"idmap",
            "atm2ice_vmaptype":"X",
            "atm2lnd_fmapname":"idmap",
            "atm2lnd_fmaptype":"X",
            "atm2lnd_smapname":"idmap",
            "atm2lnd_smaptype":"X",
            "atm2ocn_fmapname":"idmap",
            "atm2ocn_fmaptype":"X",
            "atm2ocn_smapname":"idmap",
            "atm2ocn_smaptype":"X",
            "atm2ocn_vmapname":"idmap",
            "atm2ocn_vmaptype":"X",
            "atm2rof_fmapname":"idmap",
            "atm2rof_fmaptype":"X",
            "atm2rof_smapname":"idmap",
            "atm2rof_smaptype":"X",
            "atm2wav_smapname":"idmap",
            "atm2wav_smaptype":"X",
            "glc2ice_fmapname":"idmap_ignore",
            "glc2ice_fmaptype":"X",
            "glc2ice_rmapname":"idmap_ignore",
            "glc2ice_rmaptype":"X",
            "glc2ice_smapname":"idmap_ignore",
            "glc2ice_smaptype":"X",
            "glc2lnd_fmapname":"idmap",
            "glc2lnd_fmaptype":"X",
            "glc2lnd_smapname":"idmap",
            "glc2lnd_smaptype":"X",
            "glc2ocn_fmapname":"idmap_ignore",
            "glc2ocn_fmaptype":"X",
            "glc2ocn_ice_rmapname":"idmap_ignore",
            "glc2ocn_ice_rmaptype":"X",
            "glc2ocn_liq_rmapname":"idmap_ignore",
            "glc2ocn_liq_rmaptype":"X",
            "glc2ocn_smapname":"idmap_ignore",
            "glc2ocn_smaptype":"X",
            "iac2atm_fmapname":"idmap",
            "iac2atm_fmaptype":"X",
            "iac2atm_smapname":"idmap",
            "iac2atm_smaptype":"X",
            "iac2lnd_fmapname":"idmap",
            "iac2lnd_fmaptype":"X",
            "iac2lnd_smapname":"idmap",
            "iac2lnd_smaptype":"X",
            "ice2atm_fmapname":"idmap",
            "ice2atm_fmaptype":"X",
            "ice2atm_smapname":"idmap",
            "ice2atm_smaptype":"X",
            "ice2wav_smapname":"idmap",
            "ice2wav_smaptype":"X",
            "lnd2atm_fmapname":"idmap",
            "lnd2atm_fmaptype":"X",
            "lnd2atm_smapname":"idmap",
            "lnd2atm_smaptype":"X",
            "lnd2glc_fmapname":"idmap",
            "lnd2glc_fmaptype":"X",
            "lnd2glc_smapname":"idmap",
            "lnd2glc_smaptype":"X",
            "lnd2rof_fmapname":"idmap",
            "lnd2rof_fmaptype":"X",
            "ocn2atm_fmapname":"idmap",
            "ocn2atm_fmaptype":"X",
            "ocn2atm_smapname":"idmap",
            "ocn2atm_smaptype":"X",
            "ocn2glc_fmapname":"idmap_ignore",
            "ocn2glc_fmaptype":"X",
            "ocn2glc_smapname":"idmap_ignore",
            "ocn2glc_smaptype":"X",
            "ocn2wav_smapname":"idmap",
            "ocn2wav_smaptype":"X",
            "rof2lnd_fmapname":"idmap",
            "rof2lnd_fmaptype":"X",
            "rof2ocn_fmapname":"idmap_ignore",
            "rof2ocn_fmaptype":"X",
            "rof2ocn_ice_rmapname":"idmap",
            "rof2ocn_ice_rmaptype":"X",
            "rof2ocn_liq_rmapname":"idmap",
            "rof2ocn_liq_rmaptype":"X",
            "wav2ocn_smapname":"idmap",
            "wav2ocn_smaptype":"X"
        }

    **Query parameters**
            * ``mexpid (int)``: experiment id value
            * ``mname (string)``: RC filename 

    .. note::

       note

.. envvar:: /replaysh/<int:mexpid>

    Get replay sh script page

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/replaysh/<int:mexpid>

    **Example response**:

    .. sourcecode:: bash

        #!/bin/bash

        set -e

        # Created 2022-06-08 14:53:39

        CASEDIR="/global/cscratch1/sd/petercal/e3sm_scratch/cori-knl/F2010-SCREAMv1.ne4_ne4.16x1.test1"

        /global/homes/p/petercal/gitwork/scream//cime/scripts/create_newcase --case F2010-SCREAMv1.ne4_ne4.16x1.test1 --compset F2010-SCREAMv1 --res ne4_ne4 --pecount 16x1 --compiler intel --walltime 00:30 --queue debug

        cd "${CASEDIR}"

        ./case.setup

        ./case.build

        ./case.submit

    **Query parameters**
            * ``mexpid (int)``: experiment id value

    .. note::

       note

.. envvar:: /scorpio/<int:mexpid>/<name>

    Get scorpio stats page

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/scorpio/<int:mexpid>/<name>

    **Example response**:

    .. sourcecode:: text

        scorpioIOpage.html

    **Query parameters**
            * ``mexpid (int)``: experiment id value
            * ``name (string)``: scorpio filename 

    .. note::

       note

.. envvar:: /search/<searchQuery>

    The search page! This is the primary navigation page for the site. It changes depending on where the user is on the site.

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/search/<searchQuery>

    **Example response**:

    .. sourcecode:: text

        home page navigation for PACE

    **Query parameters**
            * ``searchQuery (string)``: search query strings

    .. note::

       note

.. envvar:: /summaryQuery/<int:expID>/<rank>/

    Rest api to retrives a model-timing tree in json from the database

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/summaryQuery/<int:expID>/<rank>/

    **Example response**:

    .. sourcecode:: json

        {
            "obj":[
                [
                    {
                        "name":"CPL:INIT",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":1.0,
                        "recurse":false,
                        "wallClock":156.351669,
                        "max":156.351669,
                        "min":156.351669,
                        "utrOverhead":0.0
                        },
                        "children":[
                        {
                            "name":"CPL:cime_pre_init1",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":1.0,
                                "recurse":false,
                                "wallClock":9.745003,
                                "max":9.745003,
                                "min":9.745003,
                                "utrOverhead":0.0
                            },
                            "children":[
                                {
                                    "name":"CPL:mpi_init",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":8.397,
                                    "max":8.397,
                                    "min":8.397,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    
                                    ]
                                }
                            ]
                        },
                        {
                            "name":"CPL:ESMF_Initialize",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":1.0,
                                "recurse":false,
                                "wallClock":0.0,
                                "max":0.0,
                                "min":0.0,
                                "utrOverhead":0.0
                            },
                            "children":[
                                
                            ]
                        },
                        {
                            "name":"CPL:cime_pre_init2",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":1.0,
                                "recurse":false,
                                "wallClock":0.510199,
                                "max":0.510199,
                                "min":0.510199,
                                "utrOverhead":0.0
                            },
                            "children":[
                                {
                                    "name":"CPL:seq_infodata_init",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":0.269712,
                                    "max":0.269712,
                                    "min":0.269712,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    {
                                        "name":"PIO:get_var_1d_double",
                                        "multiParent":true,
                                        "values":{
                                            "on":false,
                                            "called":4.0,
                                            "recurse":false,
                                            "wallClock":0.002535,
                                            "max":0.000879,
                                            "min":6.6e-05,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"PIO:get_var_0d_text",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":9.8e-05,
                                            "max":9.8e-05,
                                            "min":9.8e-05,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:seq_timemgr_clockInit",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":0.104025,
                                    "max":0.104025,
                                    "min":0.104025,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    {
                                        "name":"PIO:get_var_1d_int",
                                        "multiParent":true,
                                        "values":{
                                            "on":false,
                                            "called":7.0,
                                            "recurse":false,
                                            "wallClock":0.006969,
                                            "max":0.00583,
                                            "min":5.5e-05,
                                            "utrOverhead":1e-06
                                        },
                                        "children":[
                                            {
                                                "name":"PIO:PIOc_get_vars_tc",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":12.0,
                                                "recurse":false,
                                                "wallClock":0.003488,
                                                "max":0.000827,
                                                "min":3.7e-05,
                                                "utrOverhead":1e-06
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    }
                                    ]
                                }
                            ]
                        },
                        {
                            "name":"CPL:cime_init",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":1.0,
                                "recurse":false,
                                "wallClock":146.096466,
                                "max":146.096466,
                                "min":146.096466,
                                "utrOverhead":0.0
                            },
                            "children":[
                                {
                                    "name":"CPL:init_comps",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":143.496506,
                                    "max":143.496506,
                                    "min":143.496506,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:comp_init_pre_all",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":1.7e-05,
                                            "max":1.7e-05,
                                            "min":1.7e-05,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_init_cc_atm",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":59.907314,
                                            "max":59.907314,
                                            "min":59.907314,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"a_i:comp_init",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":1.0,
                                                "recurse":false,
                                                "wallClock":59.907154,
                                                "max":59.907154,
                                                "min":59.907154,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                {
                                                    "name":"a_i:datm_readnml",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":0.50923,
                                                        "max":0.50923,
                                                        "min":0.50923,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"a_i:DATM_INIT",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":59.396839,
                                                        "max":59.396839,
                                                        "min":59.396839,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"a_i:datm_strdata_init",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":58.257004,
                                                            "max":58.257004,
                                                            "min":58.257004,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"a_i:PIO:initdecomp_dof",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":15.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.043377,
                                                                    "max":0.01535,
                                                                    "min":0.001661,
                                                                    "utrOverhead":1e-06
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"a_i:PIO:PIOc_initdecomp",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":15.0,
                                                                        "recurse":false,
                                                                        "wallClock":0.043347,
                                                                        "max":0.015344,
                                                                        "min":0.00166,
                                                                        "utrOverhead":1e-06
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"a_i:PIO:box_rearrange_create",
                                                                            "multiParent":false,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":15.0,
                                                                                "recurse":false,
                                                                                "wallClock":0.040081,
                                                                                "max":0.014411,
                                                                                "min":0.001649,
                                                                                "utrOverhead":1e-06
                                                                            },
                                                                            "children":[
                                                                                {
                                                                                    "name":"a_i:PIO:pio_swapm",
                                                                                    "multiParent":true,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":87.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":0.036115,
                                                                                    "max":0.011435,
                                                                                    "min":3.9e-05,
                                                                                    "utrOverhead":7e-06
                                                                                    },
                                                                                    "children":[
                                                                                    
                                                                                    ]
                                                                                }
                                                                            ]
                                                                        }
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"a_i:datm_initgsmaps",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.000241,
                                                            "max":0.000241,
                                                            "min":0.000241,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"a_i:datm_initmctdom",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.000259,
                                                            "max":0.000259,
                                                            "min":0.000259,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"a_i:datm_initmctavs",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.000674,
                                                            "max":0.000674,
                                                            "min":0.000674,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"a_i:DATM_RUN",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":1.104809,
                                                            "max":1.104809,
                                                            "min":1.104809,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"a_i:datm_run1",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":1.0,
                                                                    "recurse":false,
                                                                    "wallClock":7e-06,
                                                                    "max":7e-06,
                                                                    "min":7e-06,
                                                                    "utrOverhead":0.0
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            },
                                                            {
                                                                "name":"a_i:datm",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":1.0,
                                                                    "recurse":false,
                                                                    "wallClock":1.104663,
                                                                    "max":1.104663,
                                                                    "min":1.104663,
                                                                    "utrOverhead":0.0
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"a_i:datm_strdata_advance",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":1.0,
                                                                        "recurse":false,
                                                                        "wallClock":1.101394,
                                                                        "max":1.101394,
                                                                        "min":1.101394,
                                                                        "utrOverhead":0.0
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"a_i:datm_strd_adv_total",
                                                                            "multiParent":false,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":1.0,
                                                                                "recurse":false,
                                                                                "wallClock":1.101392,
                                                                                "max":1.101392,
                                                                                "min":1.101392,
                                                                                "utrOverhead":0.0
                                                                            },
                                                                            "children":[
                                                                                {
                                                                                    "name":"a_i:datm_strd_adv_readLBUB",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":5.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":0.931391,
                                                                                    "max":0.568347,
                                                                                    "min":0.007121,
                                                                                    "utrOverhead":0.0
                                                                                    },
                                                                                    "children":[
                                                                                    {
                                                                                        "name":"a_i:datm_readLBUB_setup",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":5.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":3e-06,
                                                                                            "max":1e-06,
                                                                                            "min":0.0,
                                                                                            "utrOverhead":0.0
                                                                                        },
                                                                                        "children":[
                                                                                            
                                                                                        ]
                                                                                    },
                                                                                    {
                                                                                        "name":"a_i:datm_readLBUB_fbound",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":5.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":2.9e-05,
                                                                                            "max":7e-06,
                                                                                            "min":4e-06,
                                                                                            "utrOverhead":0.0
                                                                                        },
                                                                                        "children":[
                                                                                            
                                                                                        ]
                                                                                    },
                                                                                    {
                                                                                        "name":"a_i:datm_readLBUB_bcast",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":5.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":4e-05,
                                                                                            "max":1e-05,
                                                                                            "min":5e-06,
                                                                                            "utrOverhead":0.0
                                                                                        },
                                                                                        "children":[
                                                                                            
                                                                                        ]
                                                                                    },
                                                                                    {
                                                                                        "name":"a_i:datm_readLBUB_LB_setup",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":5.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":0.002332,
                                                                                            "max":0.000669,
                                                                                            "min":0.00016,
                                                                                            "utrOverhead":0.0
                                                                                        },
                                                                                        "children":[
                                                                                            
                                                                                        ]
                                                                                    },
                                                                                    {
                                                                                        "name":"a_i:datm_readLBUB_LB_readpio",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":5.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":0.588456,
                                                                                            "max":0.313204,
                                                                                            "min":0.00536,
                                                                                            "utrOverhead":0.0
                                                                                        },
                                                                                        "children":[
                                                                                            {
                                                                                                "name":"a_i:PIO:openfile",
                                                                                                "multiParent":true,
                                                                                                "values":{
                                                                                                "on":false,
                                                                                                "called":7.0,
                                                                                                "recurse":false,
                                                                                                "wallClock":0.407632,
                                                                                                "max":0.100832,
                                                                                                "min":0.003659,
                                                                                                "utrOverhead":1e-06
                                                                                                },
                                                                                                "children":[
                                                                                                
                                                                                                ]
                                                                                            },
                                                                                            {
                                                                                                "name":"a_i:PIO:read_darray_1d_real",
                                                                                                "multiParent":true,
                                                                                                "values":{
                                                                                                "on":false,
                                                                                                "called":40.0,
                                                                                                "recurse":false,
                                                                                                "wallClock":0.511919,
                                                                                                "max":0.072278,
                                                                                                "min":0.000315,
                                                                                                "utrOverhead":3e-06
                                                                                                },
                                                                                                "children":[
                                                                                                {
                                                                                                    "name":"a_i:PIO:PIOc_read_darray",
                                                                                                    "multiParent":true,
                                                                                                    "values":{
                                                                                                        "on":false,
                                                                                                        "called":42.0,
                                                                                                        "recurse":false,
                                                                                                        "wallClock":0.514638,
                                                                                                        "max":0.072274,
                                                                                                        "min":0.000314,
                                                                                                        "utrOverhead":3e-06
                                                                                                    },
                                                                                                    "children":[
                                                                                                        {
                                                                                                            "name":"a_i:PIO:read_darray_nc_serial",
                                                                                                            "multiParent":false,
                                                                                                            "values":{
                                                                                                            "on":false,
                                                                                                            "called":42.0,
                                                                                                            "recurse":false,
                                                                                                            "wallClock":0.508048,
                                                                                                            "max":0.072002,
                                                                                                            "min":0.000256,
                                                                                                            "utrOverhead":3e-06
                                                                                                            },
                                                                                                            "children":[
                                                                                                            
                                                                                                            ]
                                                                                                        },
                                                                                                        {
                                                                                                            "name":"a_i:PIO:rearrange_io2comp",
                                                                                                            "multiParent":false,
                                                                                                            "values":{
                                                                                                            "on":false,
                                                                                                            "called":42.0,
                                                                                                            "recurse":false,
                                                                                                            "wallClock":0.00434,
                                                                                                            "max":0.00054,
                                                                                                            "min":4.1e-05,
                                                                                                            "utrOverhead":3e-06
                                                                                                            },
                                                                                                            "children":[
                                                                                                            
                                                                                                            ]
                                                                                                        }
                                                                                                    ]
                                                                                                }
                                                                                                ]
                                                                                            },
                                                                                            {
                                                                                                "name":"a_i:PIO:read_darray_1d_double",
                                                                                                "multiParent":true,
                                                                                                "values":{
                                                                                                "on":false,
                                                                                                "called":2.0,
                                                                                                "recurse":false,
                                                                                                "wallClock":0.002837,
                                                                                                "max":0.001556,
                                                                                                "min":0.001282,
                                                                                                "utrOverhead":0.0
                                                                                                },
                                                                                                "children":[
                                                                                                
                                                                                                ]
                                                                                            }
                                                                                        ]
                                                                                    },
                                                                                    {
                                                                                        "name":"a_i:datm_readLBUB_UB_setup",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":5.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":0.00206,
                                                                                            "max":0.000745,
                                                                                            "min":0.000166,
                                                                                            "utrOverhead":0.0
                                                                                        },
                                                                                        "children":[
                                                                                            
                                                                                        ]
                                                                                    },
                                                                                    {
                                                                                        "name":"a_i:datm_readLBUB_UB_readpio",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":5.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":0.338397,
                                                                                            "max":0.253699,
                                                                                            "min":0.001413,
                                                                                            "utrOverhead":0.0
                                                                                        },
                                                                                        "children":[
                                                                                            {
                                                                                                "name":"a_i:PIO:closefile",
                                                                                                "multiParent":false,
                                                                                                "values":{
                                                                                                "on":false,
                                                                                                "called":2.0,
                                                                                                "recurse":false,
                                                                                                "wallClock":0.001359,
                                                                                                "max":0.000691,
                                                                                                "min":0.000668,
                                                                                                "utrOverhead":0.0
                                                                                                },
                                                                                                "children":[
                                                                                                {
                                                                                                    "name":"a_i:PIO:PIOc_closefile",
                                                                                                    "multiParent":false,
                                                                                                    "values":{
                                                                                                        "on":false,
                                                                                                        "called":2.0,
                                                                                                        "recurse":false,
                                                                                                        "wallClock":0.001356,
                                                                                                        "max":0.000689,
                                                                                                        "min":0.000666,
                                                                                                        "utrOverhead":0.0
                                                                                                    },
                                                                                                    "children":[
                                                                                                        
                                                                                                    ]
                                                                                                }
                                                                                                ]
                                                                                            }
                                                                                        ]
                                                                                    },
                                                                                    {
                                                                                        "name":"a_i:datm_readLBUB_filemgt",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":5.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":5e-06,
                                                                                            "max":2e-06,
                                                                                            "min":0.0,
                                                                                            "utrOverhead":0.0
                                                                                        },
                                                                                        "children":[
                                                                                            
                                                                                        ]
                                                                                    }
                                                                                    ]
                                                                                },
                                                                                {
                                                                                    "name":"a_i:datm_strd_adv_fill",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":5.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":0.001027,
                                                                                    "max":0.00023,
                                                                                    "min":0.000159,
                                                                                    "utrOverhead":0.0
                                                                                    },
                                                                                    "children":[
                                                                                    
                                                                                    ]
                                                                                },
                                                                                {
                                                                                    "name":"a_i:datm_strd_adv_map",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":5.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":0.163052,
                                                                                    "max":0.072403,
                                                                                    "min":0.000542,
                                                                                    "utrOverhead":0.0
                                                                                    },
                                                                                    "children":[
                                                                                    
                                                                                    ]
                                                                                },
                                                                                {
                                                                                    "name":"a_i:datm_strd_adv_coszen",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":1.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":0.005582,
                                                                                    "max":0.005582,
                                                                                    "min":0.005582,
                                                                                    "utrOverhead":0.0
                                                                                    },
                                                                                    "children":[
                                                                                    {
                                                                                        "name":"a_i:datm_strd_adv_coszenC",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":1.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":0.000418,
                                                                                            "max":0.000418,
                                                                                            "min":0.000418,
                                                                                            "utrOverhead":0.0
                                                                                        },
                                                                                        "children":[
                                                                                            
                                                                                        ]
                                                                                    },
                                                                                    {
                                                                                        "name":"a_i:datm_strd_adv_coszenN",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":1.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":0.005065,
                                                                                            "max":0.005065,
                                                                                            "min":0.005065,
                                                                                            "utrOverhead":0.0
                                                                                        },
                                                                                        "children":[
                                                                                            
                                                                                        ]
                                                                                    }
                                                                                    ]
                                                                                },
                                                                                {
                                                                                    "name":"a_i:datm_strd_adv_tint",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":4.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":0.000296,
                                                                                    "max":0.000182,
                                                                                    "min":2.3e-05,
                                                                                    "utrOverhead":0.0
                                                                                    },
                                                                                    "children":[
                                                                                    
                                                                                    ]
                                                                                }
                                                                            ]
                                                                        }
                                                                        ]
                                                                    },
                                                                    {
                                                                        "name":"a_i:datm_scatter",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":1.0,
                                                                        "recurse":false,
                                                                        "wallClock":0.001968,
                                                                        "max":0.001968,
                                                                        "min":0.001968,
                                                                        "utrOverhead":0.0
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    },
                                                                    {
                                                                        "name":"a_i:datm_datamode",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":1.0,
                                                                        "recurse":false,
                                                                        "wallClock":0.001294,
                                                                        "max":0.001294,
                                                                        "min":0.001294,
                                                                        "utrOverhead":0.0
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    }
                                                                ]
                                                            },
                                                            {
                                                                "name":"a_i:datm_run2",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":1.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.000136,
                                                                    "max":0.000136,
                                                                    "min":0.000136,
                                                                    "utrOverhead":0.0
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_init_cc_lnd",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":22.406565,
                                            "max":22.406565,
                                            "min":22.406565,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"l_i:comp_init",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":1.0,
                                                "recurse":false,
                                                "wallClock":22.404451,
                                                "max":22.404451,
                                                "min":22.404451,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                {
                                                    "name":"l_i:elm_init1",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":8.44127,
                                                        "max":8.44127,
                                                        "min":8.44127,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"l_i:PIO:get_var_2d_int",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.043976,
                                                            "max":0.043976,
                                                            "min":0.043976,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:read_darray_3d_double",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":18.0,
                                                            "recurse":false,
                                                            "wallClock":2.536885,
                                                            "max":0.256834,
                                                            "min":0.097321,
                                                            "utrOverhead":1e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:read_darray_3d_int",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.188541,
                                                            "max":0.188541,
                                                            "min":0.188541,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:read_darray_4d_double",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":14.0,
                                                            "recurse":false,
                                                            "wallClock":3.178159,
                                                            "max":0.414455,
                                                            "min":0.142024,
                                                            "utrOverhead":1e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:get_var_1d_double",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":150.0,
                                                            "recurse":false,
                                                            "wallClock":0.034564,
                                                            "max":0.001124,
                                                            "min":8.3e-05,
                                                            "utrOverhead":1.2e-05
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:get_var_1d_int",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":7.0,
                                                            "recurse":false,
                                                            "wallClock":0.002105,
                                                            "max":0.00067,
                                                            "min":8.5e-05,
                                                            "utrOverhead":1e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:gather_1darray_int_total",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":5.0,
                                                            "recurse":false,
                                                            "wallClock":0.287463,
                                                            "max":0.059655,
                                                            "min":0.056025,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:scatter_1darray_int_total",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":5.0,
                                                            "recurse":false,
                                                            "wallClock":0.094967,
                                                            "max":0.019356,
                                                            "min":0.018151,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:init_filters",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.000323,
                                                            "max":0.000323,
                                                            "min":0.000323,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"l_i:elm_init2",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":13.922498,
                                                        "max":13.922498,
                                                        "min":13.922498,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"l_i:PIO:openfile",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":23.0,
                                                            "recurse":false,
                                                            "wallClock":0.773331,
                                                            "max":0.422859,
                                                            "min":0.003578,
                                                            "utrOverhead":2e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:closefile",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":20.0,
                                                            "recurse":false,
                                                            "wallClock":0.053693,
                                                            "max":0.007594,
                                                            "min":0.000937,
                                                            "utrOverhead":2e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l_i:PIO:PIOc_closefile",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":20.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.053648,
                                                                    "max":0.007581,
                                                                    "min":0.000936,
                                                                    "utrOverhead":2e-06
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:initdecomp_dof",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":26.0,
                                                            "recurse":false,
                                                            "wallClock":1.197797,
                                                            "max":0.167934,
                                                            "min":0.024831,
                                                            "utrOverhead":2e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l_i:PIO:PIOc_initdecomp",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":26.0,
                                                                    "recurse":false,
                                                                    "wallClock":1.197679,
                                                                    "max":0.16793,
                                                                    "min":0.024828,
                                                                    "utrOverhead":2e-06
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"l_i:PIO:box_rearrange_create",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":26.0,
                                                                        "recurse":false,
                                                                        "wallClock":1.098163,
                                                                        "max":0.167691,
                                                                        "min":0.024551,
                                                                        "utrOverhead":2e-06
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:read_darray_1d_double",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":79.0,
                                                            "recurse":false,
                                                            "wallClock":4.162701,
                                                            "max":0.425246,
                                                            "min":0.009123,
                                                            "utrOverhead":6e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:get_var_2d_double",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":8.0,
                                                            "recurse":false,
                                                            "wallClock":0.154585,
                                                            "max":0.076503,
                                                            "min":0.000303,
                                                            "utrOverhead":1e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:read_darray_1d_int",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":7.0,
                                                            "recurse":false,
                                                            "wallClock":0.258546,
                                                            "max":0.074596,
                                                            "min":0.011584,
                                                            "utrOverhead":1e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:get_var_1d_text",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":6.0,
                                                            "recurse":false,
                                                            "wallClock":0.012866,
                                                            "max":0.004774,
                                                            "min":0.000209,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:get_var_0d_double",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":11.0,
                                                            "recurse":false,
                                                            "wallClock":0.003116,
                                                            "max":0.000939,
                                                            "min":6.5e-05,
                                                            "utrOverhead":1e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:read_darray_2d_double",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":96.0,
                                                            "recurse":false,
                                                            "wallClock":7.428517,
                                                            "max":0.89506,
                                                            "min":0.003966,
                                                            "utrOverhead":8e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l_i:PIO:PIOc_read_darray",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":219.0,
                                                                    "recurse":false,
                                                                    "wallClock":17.879539,
                                                                    "max":0.895051,
                                                                    "min":0.003963,
                                                                    "utrOverhead":1.8e-05
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"l_i:PIO:read_darray_nc",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":219.0,
                                                                        "recurse":false,
                                                                        "wallClock":10.223714,
                                                                        "max":0.4064,
                                                                        "min":0.000573,
                                                                        "utrOverhead":1.8e-05
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    },
                                                                    {
                                                                        "name":"l_i:PIO:rearrange_io2comp",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":219.0,
                                                                        "recurse":false,
                                                                        "wallClock":7.487909,
                                                                        "max":0.806229,
                                                                        "min":0.003323,
                                                                        "utrOverhead":1.8e-05
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"l_i:PIO:pio_swapm",
                                                                            "multiParent":true,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":297.0,
                                                                                "recurse":false,
                                                                                "wallClock":7.973009,
                                                                                "max":0.806207,
                                                                                "min":0.003306,
                                                                                "utrOverhead":2.4e-05
                                                                            },
                                                                            "children":[
                                                                                
                                                                            ]
                                                                        }
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:read_darray_2d_int",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":4.0,
                                                            "recurse":false,
                                                            "wallClock":0.127544,
                                                            "max":0.058754,
                                                            "min":0.007925,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:get_var_0d_int",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":37.0,
                                                            "recurse":false,
                                                            "wallClock":0.040097,
                                                            "max":0.010446,
                                                            "min":5e-05,
                                                            "utrOverhead":3e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:init_orbd",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":5e-06,
                                                            "max":5e-06,
                                                            "min":5e-06,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:get_var_3d_double",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":3.0,
                                                            "recurse":false,
                                                            "wallClock":0.001594,
                                                            "max":0.001273,
                                                            "min":0.000156,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:init_accflds",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.000269,
                                                            "max":0.000269,
                                                            "min":0.000269,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:init_dyn_subgrid",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.000725,
                                                            "max":0.000725,
                                                            "min":0.000725,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:subgridRest_write-read",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":1.299206,
                                                            "max":1.299206,
                                                            "min":1.299206,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:PIO:get_var1_id_text",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":2101.0,
                                                            "recurse":false,
                                                            "wallClock":0.15987,
                                                            "max":0.000601,
                                                            "min":4e-05,
                                                            "utrOverhead":0.000173
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l_i:PIO:PIOc_get_vars_tc",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":2324.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.417709,
                                                                    "max":0.076429,
                                                                    "min":3.7e-05,
                                                                    "utrOverhead":0.000191
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:init_elm_interface_data & pflotran",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.0,
                                                            "max":0.0,
                                                            "min":0.0,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l_i:init_wlog",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":1.8e-05,
                                                            "max":1.8e-05,
                                                            "min":1.8e-05,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"l_i:elm_init3",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":7e-06,
                                                        "max":7e-06,
                                                        "min":7e-06,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_init_cc_rof",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":58.800415,
                                            "max":58.800415,
                                            "min":58.800415,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"r_i:comp_init",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":1.0,
                                                "recurse":false,
                                                "wallClock":58.799046,
                                                "max":58.799046,
                                                "min":58.799046,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                {
                                                    "name":"r_i:PIO:get_var_0d_int",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":14.0,
                                                        "recurse":false,
                                                        "wallClock":0.019144,
                                                        "max":0.018409,
                                                        "min":4.3e-05,
                                                        "utrOverhead":1e-06
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"r_i:mosarti_grid",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":1.248131,
                                                        "max":1.248131,
                                                        "min":1.248131,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"r_i:PIO:get_var_2d_double",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":3.0,
                                                            "recurse":false,
                                                            "wallClock":0.502257,
                                                            "max":0.197963,
                                                            "min":0.106976,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:PIO:get_var_2d_int",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":2.0,
                                                            "recurse":false,
                                                            "wallClock":0.456885,
                                                            "max":0.236965,
                                                            "min":0.21992,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"r_i:mosarti_decomp",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":0.663047,
                                                        "max":0.663047,
                                                        "min":0.663047,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"r_i:mosarti_dec_basins",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.483213,
                                                            "max":0.483213,
                                                            "min":0.483213,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:mosarti_dec_distr",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":0.077921,
                                                            "max":0.077921,
                                                            "min":0.077921,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"r_i:mosarti_print",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":0.000316,
                                                        "max":0.000316,
                                                        "min":0.000316,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"r_i:mosarti_vars",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":52.525513,
                                                        "max":52.525513,
                                                        "min":52.525513,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"r_i:mosarti_mosart_init",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":3.467677,
                                                        "max":3.467677,
                                                        "min":3.467677,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"r_i:PIO:initdecomp_dof",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":3.0,
                                                            "recurse":false,
                                                            "wallClock":0.056041,
                                                            "max":0.018805,
                                                            "min":0.018559,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"r_i:PIO:PIOc_initdecomp",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":3.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.056021,
                                                                    "max":0.0188,
                                                                    "min":0.01855,
                                                                    "utrOverhead":0.0
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"r_i:PIO:box_rearrange_create",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":3.0,
                                                                        "recurse":false,
                                                                        "wallClock":0.055418,
                                                                        "max":0.018646,
                                                                        "min":0.018341,
                                                                        "utrOverhead":0.0
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:PIO:read_darray_1d_int",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":3.0,
                                                            "recurse":false,
                                                            "wallClock":0.173218,
                                                            "max":0.097042,
                                                            "min":0.037486,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:PIO:syncfile",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":2.0,
                                                            "recurse":false,
                                                            "wallClock":2e-05,
                                                            "max":1.6e-05,
                                                            "min":4e-06,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"r_i:PIO:PIOc_sync",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":2.0,
                                                                    "recurse":false,
                                                                    "wallClock":1.7e-05,
                                                                    "max":1.4e-05,
                                                                    "min":3e-06,
                                                                    "utrOverhead":0.0
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"r_i:PIO:write_total",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":2.0,
                                                                        "recurse":false,
                                                                        "wallClock":1.6e-05,
                                                                        "max":1.3e-05,
                                                                        "min":3e-06,
                                                                        "utrOverhead":0.0
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:PIO:freedecomp",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":2.0,
                                                            "recurse":false,
                                                            "wallClock":2.2e-05,
                                                            "max":1.5e-05,
                                                            "min":8e-06,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"r_i:PIO:PIOc_freedecomp",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":2.0,
                                                                    "recurse":false,
                                                                    "wallClock":2e-05,
                                                                    "max":1.3e-05,
                                                                    "min":7e-06,
                                                                    "utrOverhead":0.0
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"r_i:mosarti_restart",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":0.721433,
                                                        "max":0.721433,
                                                        "min":0.721433,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"r_i:PIO:openfile",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":5.0,
                                                            "recurse":false,
                                                            "wallClock":0.105825,
                                                            "max":0.048125,
                                                            "min":0.001513,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:PIO:closefile",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":5.0,
                                                            "recurse":false,
                                                            "wallClock":0.002107,
                                                            "max":0.0013,
                                                            "min":0.000123,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"r_i:PIO:PIOc_closefile",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":5.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.002092,
                                                                    "max":0.001298,
                                                                    "min":0.000122,
                                                                    "utrOverhead":0.0
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:PIO:read_darray_1d_double",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":37.0,
                                                            "recurse":false,
                                                            "wallClock":1.945018,
                                                            "max":0.14477,
                                                            "min":0.01544,
                                                            "utrOverhead":3e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"r_i:PIO:PIOc_read_darray",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":40.0,
                                                                    "recurse":false,
                                                                    "wallClock":2.11787,
                                                                    "max":0.144761,
                                                                    "min":0.01543,
                                                                    "utrOverhead":3e-06
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"r_i:PIO:read_darray_nc",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":40.0,
                                                                        "recurse":false,
                                                                        "wallClock":1.082677,
                                                                        "max":0.103395,
                                                                        "min":0.0,
                                                                        "utrOverhead":3e-06
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    },
                                                                    {
                                                                        "name":"r_i:PIO:rearrange_io2comp",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":40.0,
                                                                        "recurse":false,
                                                                        "wallClock":1.032627,
                                                                        "max":0.123935,
                                                                        "min":0.002707,
                                                                        "utrOverhead":3e-06
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"r_i:PIO:pio_swapm",
                                                                            "multiParent":true,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":49.0,
                                                                                "recurse":false,
                                                                                "wallClock":1.031956,
                                                                                "max":0.122684,
                                                                                "min":1e-05,
                                                                                "utrOverhead":4e-06
                                                                            },
                                                                            "children":[
                                                                                
                                                                            ]
                                                                        }
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:PIO:get_var_1d_text",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":4.0,
                                                            "recurse":false,
                                                            "wallClock":0.0024,
                                                            "max":0.001208,
                                                            "min":9.2e-05,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:PIO:get_var_0d_double",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":5.9e-05,
                                                            "max":5.9e-05,
                                                            "min":5.9e-05,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:PIO:get_var_1d_int",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":1.0,
                                                            "recurse":false,
                                                            "wallClock":7.6e-05,
                                                            "max":7.6e-05,
                                                            "min":7.6e-05,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"r_i:PIO:get_var1_id_text",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":100.0,
                                                            "recurse":false,
                                                            "wallClock":0.00478,
                                                            "max":0.000394,
                                                            "min":1e-05,
                                                            "utrOverhead":8e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"r_i:PIO:PIOc_get_vars_tc",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":125.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.984379,
                                                                    "max":0.236932,
                                                                    "min":8e-06,
                                                                    "utrOverhead":1e-05
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"r_i:mosarti_histinit",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":1.0,
                                                        "recurse":false,
                                                        "wallClock":0.007744,
                                                        "max":0.007744,
                                                        "min":0.007744,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_init_cc_ocn",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":0.00047,
                                            "max":0.00047,
                                            "min":0.00047,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"o_i:comp_init",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":1.0,
                                                "recurse":false,
                                                "wallClock":1e-06,
                                                "max":1e-06,
                                                "min":1e-06,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_init_cc_ice",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":9.7e-05,
                                            "max":9.7e-05,
                                            "min":9.7e-05,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"i_i:comp_init",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":1.0,
                                                "recurse":false,
                                                "wallClock":1e-06,
                                                "max":1e-06,
                                                "min":1e-06,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_init_cc_glc",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":9.6e-05,
                                            "max":9.6e-05,
                                            "min":9.6e-05,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"g_i:comp_init",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":1.0,
                                                "recurse":false,
                                                "wallClock":2e-06,
                                                "max":2e-06,
                                                "min":2e-06,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_init_cc_wav",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":8e-05,
                                            "max":8e-05,
                                            "min":8e-05,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"w_i:comp_init",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":1.0,
                                                "recurse":false,
                                                "wallClock":1e-06,
                                                "max":1e-06,
                                                "min":1e-06,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_init_cc_esp",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":8.1e-05,
                                            "max":8.1e-05,
                                            "min":8.1e-05,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"e_i:comp_init",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":1.0,
                                                "recurse":false,
                                                "wallClock":3e-06,
                                                "max":3e-06,
                                                "min":3e-06,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_init_cc_iac",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":8.1e-05,
                                            "max":8.1e-05,
                                            "min":8.1e-05,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"z_i:comp_init",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":1.0,
                                                "recurse":false,
                                                "wallClock":2e-06,
                                                "max":2e-06,
                                                "min":2e-06,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_init_cx_all",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":2.381226,
                                            "max":2.381226,
                                            "min":2.381226,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"CPL:comp_list_all",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":1.1e-05,
                                            "max":1.1e-05,
                                            "min":1.1e-05,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:init_maps",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":0.258715,
                                    "max":0.258715,
                                    "min":0.258715,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"CPL:init_aream",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":0.031567,
                                    "max":0.031567,
                                    "min":0.031567,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"CPL:init_domain_check",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":0.011521,
                                    "max":0.011521,
                                    "min":0.011521,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"CPL:init_areacor",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":0.056288,
                                    "max":0.056288,
                                    "min":0.056288,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"CPL:init_fracs",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":0.002289,
                                    "max":0.002289,
                                    "min":0.002289,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"CPL:init_readrestart",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":2.238176,
                                    "max":2.238176,
                                    "min":2.238176,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:seq_rest_read-init",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":1.0,
                                            "recurse":false,
                                            "wallClock":2.238055,
                                            "max":2.238055,
                                            "min":2.238055,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"PIO:openfile",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":11.0,
                                                "recurse":false,
                                                "wallClock":0.388335,
                                                "max":0.265409,
                                                "min":0.003492,
                                                "utrOverhead":1e-06
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"PIO:get_att_id_text",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":11.0,
                                                "recurse":false,
                                                "wallClock":0.000825,
                                                "max":0.000371,
                                                "min":3.8e-05,
                                                "utrOverhead":1e-06
                                                },
                                                "children":[
                                                {
                                                    "name":"PIO:PIOc_get_att_tc",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":11.0,
                                                        "recurse":false,
                                                        "wallClock":0.000788,
                                                        "max":0.000367,
                                                        "min":3.5e-05,
                                                        "utrOverhead":1e-06
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"PIO:closefile",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":13.0,
                                                "recurse":false,
                                                "wallClock":0.167932,
                                                "max":0.05886,
                                                "min":0.001227,
                                                "utrOverhead":1e-06
                                                },
                                                "children":[
                                                {
                                                    "name":"PIO:PIOc_closefile",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":13.0,
                                                        "recurse":false,
                                                        "wallClock":0.167915,
                                                        "max":0.058859,
                                                        "min":0.001226,
                                                        "utrOverhead":1e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:PIOc_closefile_write_mode",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":2.0,
                                                            "recurse":false,
                                                            "wallClock":0.004064,
                                                            "max":0.002064,
                                                            "min":0.001999,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"PIO:initdecomp_dof",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":21.0,
                                                "recurse":false,
                                                "wallClock":0.102867,
                                                "max":0.009308,
                                                "min":0.002944,
                                                "utrOverhead":2e-06
                                                },
                                                "children":[
                                                {
                                                    "name":"PIO:PIOc_initdecomp",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":21.0,
                                                        "recurse":false,
                                                        "wallClock":0.102756,
                                                        "max":0.009304,
                                                        "min":0.002941,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:box_rearrange_create",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":21.0,
                                                            "recurse":false,
                                                            "wallClock":0.083467,
                                                            "max":0.006838,
                                                            "min":0.002901,
                                                            "utrOverhead":2e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"PIO:read_darray_1d_double",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":102.0,
                                                "recurse":false,
                                                "wallClock":1.895638,
                                                "max":0.082912,
                                                "min":0.00702,
                                                "utrOverhead":8e-06
                                                },
                                                "children":[
                                                {
                                                    "name":"PIO:PIOc_read_darray",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":102.0,
                                                        "recurse":false,
                                                        "wallClock":1.895276,
                                                        "max":0.082905,
                                                        "min":0.007017,
                                                        "utrOverhead":8e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:read_darray_nc",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":102.0,
                                                            "recurse":false,
                                                            "wallClock":1.697016,
                                                            "max":0.076032,
                                                            "min":0.00652,
                                                            "utrOverhead":8e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"PIO:rearrange_io2comp",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":102.0,
                                                            "recurse":false,
                                                            "wallClock":0.078087,
                                                            "max":0.006841,
                                                            "min":0.000413,
                                                            "utrOverhead":8e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"PIO:pio_swapm",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":179.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.273516,
                                                                    "max":0.035793,
                                                                    "min":0.00041,
                                                                    "utrOverhead":1.5e-05
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"PIO:syncfile",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":21.0,
                                                "recurse":false,
                                                "wallClock":4.00077,
                                                "max":0.71046,
                                                "min":2e-06,
                                                "utrOverhead":2e-06
                                                },
                                                "children":[
                                                {
                                                    "name":"PIO:PIOc_sync",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":21.0,
                                                        "recurse":false,
                                                        "wallClock":4.0007,
                                                        "max":0.710457,
                                                        "min":2e-06,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:write_total",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":1351.0,
                                                            "recurse":false,
                                                            "wallClock":4.094755,
                                                            "max":0.710457,
                                                            "min":1e-06,
                                                            "utrOverhead":0.000111
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"PIO:flush_output_buffer",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":54.0,
                                                                    "recurse":false,
                                                                    "wallClock":2.47115,
                                                                    "max":0.437571,
                                                                    "min":7e-06,
                                                                    "utrOverhead":4e-06
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            },
                                                            {
                                                                "name":"PIO:flush_buffer",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":14.0,
                                                                    "recurse":false,
                                                                    "wallClock":1.538111,
                                                                    "max":0.272978,
                                                                    "min":0.028738,
                                                                    "utrOverhead":1e-06
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"PIO:PIOc_write_darray_multi",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":14.0,
                                                                        "recurse":false,
                                                                        "wallClock":1.537821,
                                                                        "max":0.272957,
                                                                        "min":0.028709,
                                                                        "utrOverhead":1e-06
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"PIO:rearrange_comp2io",
                                                                            "multiParent":false,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":14.0,
                                                                                "recurse":false,
                                                                                "wallClock":0.24297,
                                                                                "max":0.038784,
                                                                                "min":0.007032,
                                                                                "utrOverhead":1e-06
                                                                            },
                                                                            "children":[
                                                                                
                                                                            ]
                                                                        },
                                                                        {
                                                                            "name":"PIO:write_darray_multi_par",
                                                                            "multiParent":false,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":14.0,
                                                                                "recurse":false,
                                                                                "wallClock":1.225467,
                                                                                "max":0.234041,
                                                                                "min":0.017976,
                                                                                "utrOverhead":1e-06
                                                                            },
                                                                            "children":[
                                                                                
                                                                            ]
                                                                        }
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"PIO:freedecomp",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":21.0,
                                                "recurse":false,
                                                "wallClock":0.002115,
                                                "max":0.000156,
                                                "min":6.7e-05,
                                                "utrOverhead":2e-06
                                                },
                                                "children":[
                                                {
                                                    "name":"PIO:PIOc_freedecomp",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":21.0,
                                                        "recurse":false,
                                                        "wallClock":0.002079,
                                                        "max":0.000154,
                                                        "min":6.6e-05,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            }
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:init_rof2lnd",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":0.000354,
                                    "max":0.000354,
                                    "min":0.000354,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    
                                    ]
                                }
                            ]
                        }
                        ]
                    },
                    {
                        "name":"CPL:cime_run_init",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":1.0,
                        "recurse":false,
                        "wallClock":0.002259,
                        "max":0.002259,
                        "min":0.002259,
                        "utrOverhead":0.0
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"CPL:INIT_sync1_tprf",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":1.0,
                        "recurse":false,
                        "wallClock":1.1e-05,
                        "max":1.1e-05,
                        "min":1.1e-05,
                        "utrOverhead":0.0
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"CPL:INIT_t_prf",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":1.0,
                        "recurse":false,
                        "wallClock":0.013232,
                        "max":0.013232,
                        "min":0.013232,
                        "utrOverhead":0.0
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"CPL:INIT_sync2_tprf",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":1.0,
                        "recurse":false,
                        "wallClock":9e-06,
                        "max":9e-06,
                        "min":9e-06,
                        "utrOverhead":0.0
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"CPL:RUN_LOOP_BSTART",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":1.0,
                        "recurse":false,
                        "wallClock":3.3e-05,
                        "max":3.3e-05,
                        "min":3.3e-05,
                        "utrOverhead":0.0
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"CPL:RUN_LOOP",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":7444.578613,
                        "max":9.664616,
                        "min":0.044833,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        {
                            "name":"CPL:CLOCK_ADVANCE",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":4.073512,
                                "max":0.0004,
                                "min":8.6e-05,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        },
                        {
                            "name":"CPL:RUN",
                            "multiParent":true,
                            "values":{
                                "on":false,
                                "called":257692.0,
                                "recurse":false,
                                "wallClock":80.576302,
                                "max":2.137479,
                                "min":1e-06,
                                "utrOverhead":0.021158
                            },
                            "children":[
                                {
                                    "name":"CPL:LNDPREP",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":43.819492,
                                    "max":0.009798,
                                    "min":0.000392,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:lndprep_atm2lnd",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":30.951294,
                                            "max":0.009495,
                                            "min":0.000141,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"CPL:lndprep_mrgx2l",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":12.700899,
                                            "max":0.000754,
                                            "min":0.000242,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:ROFPREP",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":5840.0,
                                    "recurse":false,
                                    "wallClock":13.310469,
                                    "max":0.002575,
                                    "min":0.002177,
                                    "utrOverhead":0.000479
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:rofprep_l2xavg",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":0.657334,
                                            "max":0.00018,
                                            "min":2.9e-05,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"CPL:rofprep_lnd2rof",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":2.182024,
                                            "max":0.000561,
                                            "min":0.000352,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"CPL:rofprep_atm2rof",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":3.818774,
                                            "max":0.000857,
                                            "min":0.000614,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"CPL:rofprep_mrgx2r",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":6.609942,
                                            "max":0.001391,
                                            "min":0.001067,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:LNDPOST",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":3.760536,
                                    "max":0.000365,
                                    "min":6.2e-05,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:lndpost_accl2r",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":3.692083,
                                            "max":0.000363,
                                            "min":5.9e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:ROFRUNPOST",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":5840.0,
                                    "recurse":false,
                                    "wallClock":2.023784,
                                    "max":0.001431,
                                    "min":0.000327,
                                    "utrOverhead":0.000479
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:rofpost_rof2lnd",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":2.014761,
                                            "max":0.001429,
                                            "min":0.000326,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:ROFPOST",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":0.006673,
                                    "max":2e-06,
                                    "min":0.0,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"CPL:FRACSET",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":0.114385,
                                    "max":2.3e-05,
                                    "min":2e-06,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:fracset_fracset",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":0.08047,
                                            "max":2.2e-05,
                                            "min":1e-06,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:ATMPOST",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":12.453036,
                                    "max":0.00089,
                                    "min":0.000194,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:atmpost_acca2r",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":12.3733,
                                            "max":0.000887,
                                            "min":0.000193,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:HISTORY",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":0.033449,
                                    "max":2e-05,
                                    "min":1e-06,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:cime_run_write_history",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":0.010853,
                                            "max":1.9e-05,
                                            "min":0.0,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:TSTAMP_WRITE",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":0.572128,
                                    "max":0.121519,
                                    "min":0.0,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"CPL:BARRIERALARM",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":730.0,
                                    "recurse":false,
                                    "wallClock":0.010906,
                                    "max":0.000171,
                                    "min":9e-06,
                                    "utrOverhead":6e-05
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"CPL:RESTART",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":2.0,
                                    "recurse":false,
                                    "wallClock":4.245612,
                                    "max":2.137478,
                                    "min":2.108134,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:cime_run_write_restart",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":2.0,
                                            "recurse":false,
                                            "wallClock":4.245606,
                                            "max":2.137475,
                                            "min":2.108132,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"CPL:seq_rest_write",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":2.0,
                                                "recurse":false,
                                                "wallClock":4.245382,
                                                "max":2.137375,
                                                "min":2.108007,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                {
                                                    "name":"PIO:createfile",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":2.0,
                                                        "recurse":false,
                                                        "wallClock":0.028518,
                                                        "max":0.014893,
                                                        "min":0.013626,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:PIOc_createfile",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":2.0,
                                                            "recurse":false,
                                                            "wallClock":0.028509,
                                                            "max":0.014889,
                                                            "min":0.01362,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"PIO:put_att_id_text",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":894.0,
                                                        "recurse":false,
                                                        "wallClock":0.014797,
                                                        "max":0.000156,
                                                        "min":1.4e-05,
                                                        "utrOverhead":7.3e-05
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:PIOc_put_att_tc",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":1098.0,
                                                            "recurse":false,
                                                            "wallClock":0.015475,
                                                            "max":0.000154,
                                                            "min":1.1e-05,
                                                            "utrOverhead":9e-05
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"PIO:write_total",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":1351.0,
                                                                    "recurse":false,
                                                                    "wallClock":4.094755,
                                                                    "max":0.710457,
                                                                    "min":1e-06,
                                                                    "utrOverhead":0.000111
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"PIO:flush_output_buffer",
                                                                        "multiParent":true,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":54.0,
                                                                        "recurse":false,
                                                                        "wallClock":2.47115,
                                                                        "max":0.437571,
                                                                        "min":7e-06,
                                                                        "utrOverhead":4e-06
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    },
                                                                    {
                                                                        "name":"PIO:flush_buffer",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":14.0,
                                                                        "recurse":false,
                                                                        "wallClock":1.538111,
                                                                        "max":0.272978,
                                                                        "min":0.028738,
                                                                        "utrOverhead":1e-06
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"PIO:PIOc_write_darray_multi",
                                                                            "multiParent":false,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":14.0,
                                                                                "recurse":false,
                                                                                "wallClock":1.537821,
                                                                                "max":0.272957,
                                                                                "min":0.028709,
                                                                                "utrOverhead":1e-06
                                                                            },
                                                                            "children":[
                                                                                {
                                                                                    "name":"PIO:rearrange_comp2io",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":14.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":0.24297,
                                                                                    "max":0.038784,
                                                                                    "min":0.007032,
                                                                                    "utrOverhead":1e-06
                                                                                    },
                                                                                    "children":[
                                                                                    
                                                                                    ]
                                                                                },
                                                                                {
                                                                                    "name":"PIO:write_darray_multi_par",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":14.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":1.225467,
                                                                                    "max":0.234041,
                                                                                    "min":0.017976,
                                                                                    "utrOverhead":1e-06
                                                                                    },
                                                                                    "children":[
                                                                                    
                                                                                    ]
                                                                                }
                                                                            ]
                                                                        }
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"PIO:put_att_id_double",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":204.0,
                                                        "recurse":false,
                                                        "wallClock":0.003302,
                                                        "max":5.8e-05,
                                                        "min":1.5e-05,
                                                        "utrOverhead":1.7e-05
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"PIO:put_var_0d_double",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":4.0,
                                                        "recurse":false,
                                                        "wallClock":0.000447,
                                                        "max":0.000116,
                                                        "min":0.000109,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"PIO:put_var_0d_text",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":2.0,
                                                        "recurse":false,
                                                        "wallClock":0.000446,
                                                        "max":0.000226,
                                                        "min":0.00022,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"PIO:put_var_0d_int",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":14.0,
                                                        "recurse":false,
                                                        "wallClock":0.003345,
                                                        "max":0.001291,
                                                        "min":0.000106,
                                                        "utrOverhead":1e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:PIOc_put_vars_tc",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":24.0,
                                                            "recurse":false,
                                                            "wallClock":0.004623,
                                                            "max":0.001269,
                                                            "min":9.6e-05,
                                                            "utrOverhead":2e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"PIO:put_var_1d_double",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":4.0,
                                                        "recurse":false,
                                                        "wallClock":0.000982,
                                                        "max":0.000284,
                                                        "min":0.000226,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"PIO:write_darray_double",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":204.0,
                                                        "recurse":false,
                                                        "wallClock":0.041874,
                                                        "max":0.000585,
                                                        "min":0.000113,
                                                        "utrOverhead":1.7e-05
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:PIOc_write_darray",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":204.0,
                                                            "recurse":false,
                                                            "wallClock":0.041307,
                                                            "max":0.000582,
                                                            "min":0.000111,
                                                            "utrOverhead":1.7e-05
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"PIO:initdecomp_dof",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":21.0,
                                                        "recurse":false,
                                                        "wallClock":0.102867,
                                                        "max":0.009308,
                                                        "min":0.002944,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:PIOc_initdecomp",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":21.0,
                                                            "recurse":false,
                                                            "wallClock":0.102756,
                                                            "max":0.009304,
                                                            "min":0.002941,
                                                            "utrOverhead":2e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"PIO:box_rearrange_create",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":21.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.083467,
                                                                    "max":0.006838,
                                                                    "min":0.002901,
                                                                    "utrOverhead":2e-06
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"PIO:syncfile",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":21.0,
                                                        "recurse":false,
                                                        "wallClock":4.00077,
                                                        "max":0.71046,
                                                        "min":2e-06,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:PIOc_sync",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":21.0,
                                                            "recurse":false,
                                                            "wallClock":4.0007,
                                                            "max":0.710457,
                                                            "min":2e-06,
                                                            "utrOverhead":2e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"PIO:write_total",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":1351.0,
                                                                    "recurse":false,
                                                                    "wallClock":4.094755,
                                                                    "max":0.710457,
                                                                    "min":1e-06,
                                                                    "utrOverhead":0.000111
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"PIO:flush_output_buffer",
                                                                        "multiParent":true,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":54.0,
                                                                        "recurse":false,
                                                                        "wallClock":2.47115,
                                                                        "max":0.437571,
                                                                        "min":7e-06,
                                                                        "utrOverhead":4e-06
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    },
                                                                    {
                                                                        "name":"PIO:flush_buffer",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":14.0,
                                                                        "recurse":false,
                                                                        "wallClock":1.538111,
                                                                        "max":0.272978,
                                                                        "min":0.028738,
                                                                        "utrOverhead":1e-06
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"PIO:PIOc_write_darray_multi",
                                                                            "multiParent":false,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":14.0,
                                                                                "recurse":false,
                                                                                "wallClock":1.537821,
                                                                                "max":0.272957,
                                                                                "min":0.028709,
                                                                                "utrOverhead":1e-06
                                                                            },
                                                                            "children":[
                                                                                {
                                                                                    "name":"PIO:rearrange_comp2io",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":14.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":0.24297,
                                                                                    "max":0.038784,
                                                                                    "min":0.007032,
                                                                                    "utrOverhead":1e-06
                                                                                    },
                                                                                    "children":[
                                                                                    
                                                                                    ]
                                                                                },
                                                                                {
                                                                                    "name":"PIO:write_darray_multi_par",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":14.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":1.225467,
                                                                                    "max":0.234041,
                                                                                    "min":0.017976,
                                                                                    "utrOverhead":1e-06
                                                                                    },
                                                                                    "children":[
                                                                                    
                                                                                    ]
                                                                                }
                                                                            ]
                                                                        }
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"PIO:freedecomp",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":21.0,
                                                        "recurse":false,
                                                        "wallClock":0.002115,
                                                        "max":0.000156,
                                                        "min":6.7e-05,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"PIO:PIOc_freedecomp",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":21.0,
                                                            "recurse":false,
                                                            "wallClock":0.002079,
                                                            "max":0.000154,
                                                            "min":6.6e-05,
                                                            "utrOverhead":2e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            }
                                        ]
                                    }
                                    ]
                                }
                            ]
                        },
                        {
                            "name":"CPL:COMM",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":116800.0,
                                "recurse":false,
                                "wallClock":887.029175,
                                "max":0.917072,
                                "min":0.000524,
                                "utrOverhead":0.00959
                            },
                            "children":[
                                {
                                    "name":"CPL:C2L",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":235.36058,
                                    "max":0.039008,
                                    "min":0.000622,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:c2l_lndx2lndl",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":234.273956,
                                            "max":0.038646,
                                            "min":0.000596,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"CPL:c2l_infoexch",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":0.967046,
                                            "max":0.006058,
                                            "min":1.5e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:C2R",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":5840.0,
                                    "recurse":false,
                                    "wallClock":301.172821,
                                    "max":0.065274,
                                    "min":0.050092,
                                    "utrOverhead":0.000479
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:c2r_rofx2rofr",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":301.00235,
                                            "max":0.065246,
                                            "min":0.05006,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"CPL:c2r_infoexch",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":0.148721,
                                            "max":5.1e-05,
                                            "min":2.2e-05,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:L2C",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":253.132492,
                                    "max":0.917071,
                                    "min":0.001265,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:l2c_lndl2lndx",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":252.918015,
                                            "max":0.917061,
                                            "min":0.001259,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"lnd2cpl_run",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":0.086436,
                                            "max":0.000215,
                                            "min":1e-06,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:R2C",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":5840.0,
                                    "recurse":false,
                                    "wallClock":77.881248,
                                    "max":0.021188,
                                    "min":0.003139,
                                    "utrOverhead":0.000479
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:r2c_rofr2rofx",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":77.848976,
                                            "max":0.021183,
                                            "min":0.003134,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"CPL:r2c_infoexch",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":0.009832,
                                            "max":9e-06,
                                            "min":1e-06,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"CPL:A2C",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":19.362507,
                                    "max":0.006275,
                                    "min":0.000523,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    {
                                        "name":"CPL:a2c_atma2atmx",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":17.87616,
                                            "max":0.000757,
                                            "min":0.000501,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"CPL:a2c_infoexch",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":1.389975,
                                            "max":0.005767,
                                            "min":1.8e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                }
                            ]
                        },
                        {
                            "name":"CPL:LND_RUN",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":1217.911255,
                                "max":7.424982,
                                "min":0.027363,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                {
                                    "name":"l:lc_lnd_import",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":2.172467,
                                    "max":0.000352,
                                    "min":5.3e-05,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"l:elm_run",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":1208.275391,
                                    "max":7.424743,
                                    "min":0.02708,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    {
                                        "name":"l:shr_orb_decl",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":0.139288,
                                            "max":2.5e-05,
                                            "min":1e-06,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:interpMonthlyVeg",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":46.630493,
                                            "max":2.518194,
                                            "min":1e-06,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            {
                                                "name":"l:readMonthlyVeg",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":25.0,
                                                "recurse":false,
                                                "wallClock":46.59483,
                                                "max":2.518189,
                                                "min":1.277601,
                                                "utrOverhead":2e-06
                                                },
                                                "children":[
                                                {
                                                    "name":"l:PIO:openfile",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":25.0,
                                                        "recurse":false,
                                                        "wallClock":0.300789,
                                                        "max":0.021524,
                                                        "min":0.004609,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"l:PIO:initdecomp_dof",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":8.0,
                                                        "recurse":false,
                                                        "wallClock":0.2362,
                                                        "max":0.036309,
                                                        "min":0.025829,
                                                        "utrOverhead":1e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"l:PIO:PIOc_initdecomp",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":8.0,
                                                            "recurse":false,
                                                            "wallClock":0.236168,
                                                            "max":0.036304,
                                                            "min":0.025827,
                                                            "utrOverhead":1e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l:PIO:box_rearrange_create",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":8.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.227804,
                                                                    "max":0.030773,
                                                                    "min":0.025643,
                                                                    "utrOverhead":1e-06
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"l:PIO:read_darray_3d_double",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":200.0,
                                                        "recurse":false,
                                                        "wallClock":45.302647,
                                                        "max":0.580054,
                                                        "min":0.08858,
                                                        "utrOverhead":1.6e-05
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"l:PIO:PIOc_read_darray",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":200.0,
                                                            "recurse":false,
                                                            "wallClock":45.300491,
                                                            "max":0.580043,
                                                            "min":0.08857,
                                                            "utrOverhead":1.6e-05
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l:PIO:read_darray_nc",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":200.0,
                                                                    "recurse":false,
                                                                    "wallClock":43.35717,
                                                                    "max":0.570212,
                                                                    "min":0.078354,
                                                                    "utrOverhead":1.6e-05
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            },
                                                            {
                                                                "name":"l:PIO:rearrange_io2comp",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":200.0,
                                                                    "recurse":false,
                                                                    "wallClock":1.8455,
                                                                    "max":0.021846,
                                                                    "min":0.007588,
                                                                    "utrOverhead":1.6e-05
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"l:PIO:pio_swapm",
                                                                        "multiParent":true,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":432.0,
                                                                        "recurse":false,
                                                                        "wallClock":12.705971,
                                                                        "max":0.309958,
                                                                        "min":0.004169,
                                                                        "utrOverhead":3.5e-05
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"l:PIO:closefile",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":53.0,
                                                        "recurse":false,
                                                        "wallClock":42.619278,
                                                        "max":5.393831,
                                                        "min":0.002387,
                                                        "utrOverhead":4e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"l:PIO:PIOc_closefile",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":53.0,
                                                            "recurse":false,
                                                            "wallClock":42.619087,
                                                            "max":5.393827,
                                                            "min":0.002384,
                                                            "utrOverhead":4e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l:PIO:PIOc_closefile_write_mode",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":28.0,
                                                                    "recurse":false,
                                                                    "wallClock":42.490864,
                                                                    "max":5.393698,
                                                                    "min":0.002313,
                                                                    "utrOverhead":2e-06
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"l:decomp_vert",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":0.308155,
                                            "max":4.5e-05,
                                            "min":3e-06,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:beggridwbal",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":5.939963,
                                            "max":0.000397,
                                            "min":0.000158,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:cnpinit",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":0.034199,
                                            "max":2.1e-05,
                                            "min":1e-06,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            {
                                                "name":"l:cnpvegsumm",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":0.004341,
                                                "max":1e-06,
                                                "min":0.0,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"l:dyn_subgrid",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":44.732822,
                                            "max":0.001661,
                                            "min":0.001197,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:begwbal",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":1.01526,
                                            "max":0.000352,
                                            "min":2.6e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:begcnpbal",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":0.005706,
                                            "max":1e-06,
                                            "min":0.0,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:drvinit",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":4.667262,
                                            "max":0.000556,
                                            "min":7.8e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:canhydro",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":9.801005,
                                            "max":0.000838,
                                            "min":0.000201,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:surfrad",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":22.104914,
                                            "max":0.001041,
                                            "min":0.000239,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:bgp1",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":9.183909,
                                            "max":0.000541,
                                            "min":0.00016,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:bgflux",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":23.014589,
                                            "max":0.001212,
                                            "min":0.000402,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:canflux",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":358.40033,
                                            "max":0.02274,
                                            "min":0.005275,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            {
                                                "name":"l:can_iter",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":304.731842,
                                                "max":0.020983,
                                                "min":0.003919,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"l:uflux",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":7.22536,
                                            "max":0.000476,
                                            "min":0.000108,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:bgplake",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":33.418346,
                                            "max":0.002352,
                                            "min":0.00064,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            {
                                                "name":"l:bgc",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":28.341902,
                                                "max":0.002217,
                                                "min":0.000536,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"l:soiltemperature",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":107.608009,
                                            "max":0.004134,
                                            "min":0.001625,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            {
                                                "name":"l:SoilThermProp",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":16.602871,
                                                "max":0.000936,
                                                "min":0.000274,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"l:SoilTempBandDiag",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":70080.0,
                                                "recurse":false,
                                                "wallClock":21.973654,
                                                "max":0.001006,
                                                "min":5.6e-05,
                                                "utrOverhead":0.005754
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"l:PhaseChangeH2osfc",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":0.113367,
                                                "max":4.7e-05,
                                                "min":1e-06,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"l:PhaseChangebeta",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":7.432838,
                                                "max":0.000653,
                                                "min":8.4e-05,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"l:bgp2",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":12.199331,
                                            "max":0.000824,
                                            "min":0.00016,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            {
                                                "name":"l:bgp2_loop_1",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":1.786559,
                                                "max":0.000376,
                                                "min":2.2e-05,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"l:bgp2_loop_2",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":3.085075,
                                                "max":0.0004,
                                                "min":3.2e-05,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"l:bgp2_loop_3",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":5.599009,
                                                "max":0.000546,
                                                "min":7.7e-05,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"l:bgp2_loop_4",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":1.227564,
                                                "max":0.000353,
                                                "min":1.7e-05,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"l:patch2col",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":6.751622,
                                            "max":0.00056,
                                            "min":0.000111,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:hydro without drainage",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":66.552658,
                                            "max":0.002628,
                                            "min":0.001092,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:hylake",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":4.474916,
                                            "max":0.000603,
                                            "min":5.9e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:snow_init",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":2.943211,
                                            "max":0.000507,
                                            "min":4.3e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:ecosysdyn",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":2.386994,
                                            "max":0.000474,
                                            "min":2.1e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:depvel",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":70080.0,
                                            "recurse":false,
                                            "wallClock":0.078725,
                                            "max":5.3e-05,
                                            "min":0.0,
                                            "utrOverhead":0.005754
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:hydro2 drainage",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":6.314667,
                                            "max":0.000679,
                                            "min":8.4e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:balchk",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":5.691676,
                                            "max":0.000534,
                                            "min":7.8e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:gridbalchk",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":5.520859,
                                            "max":0.000661,
                                            "min":7.5e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:surfalb",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":71.437393,
                                            "max":0.003563,
                                            "min":0.000619,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:urbsurfalb",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":17.979479,
                                            "max":0.001268,
                                            "min":0.000187,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:lnd2atm",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":48.410282,
                                            "max":0.001732,
                                            "min":0.001324,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:wrtdiag",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":5.067086,
                                            "max":0.026573,
                                            "min":0.000122,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:accum",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":18.264858,
                                            "max":0.000809,
                                            "min":0.000459,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:hbuf",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":127.664536,
                                            "max":0.00411,
                                            "min":0.003508,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"l:elm_drv_io",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":48.62265,
                                            "max":7.38902,
                                            "min":3e-06,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            {
                                                "name":"l:elm_drv_io_htapes",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":36.926132,
                                                "max":2.196043,
                                                "min":2e-06,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                {
                                                    "name":"l:hist_htapes_wrapup_define",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":24.0,
                                                        "recurse":false,
                                                        "wallClock":2.203308,
                                                        "max":0.169737,
                                                        "min":0.077633,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"l:PIO:createfile",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":28.0,
                                                            "recurse":false,
                                                            "wallClock":1.202377,
                                                            "max":0.123844,
                                                            "min":0.018963,
                                                            "utrOverhead":2e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l:PIO:PIOc_createfile",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":28.0,
                                                                    "recurse":false,
                                                                    "wallClock":1.202217,
                                                                    "max":0.123838,
                                                                    "min":0.018953,
                                                                    "utrOverhead":2e-06
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"l:PIO:put_att_id_text",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":17186.0,
                                                            "recurse":false,
                                                            "wallClock":0.380964,
                                                            "max":0.000744,
                                                            "min":1.3e-05,
                                                            "utrOverhead":0.001411
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l:PIO:PIOc_put_att_tc",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":28668.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.580276,
                                                                    "max":0.007385,
                                                                    "min":1.1e-05,
                                                                    "utrOverhead":0.002354
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"l:PIO:write_total",
                                                                        "multiParent":true,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":34332.0,
                                                                        "recurse":false,
                                                                        "wallClock":46.283157,
                                                                        "max":5.393699,
                                                                        "min":1.1e-05,
                                                                        "utrOverhead":0.002819
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"l:PIO:flush_output_buffer",
                                                                            "multiParent":true,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":734.0,
                                                                                "recurse":false,
                                                                                "wallClock":11.946192,
                                                                                "max":2.527916,
                                                                                "min":8e-06,
                                                                                "utrOverhead":6e-05
                                                                            },
                                                                            "children":[
                                                                                
                                                                            ]
                                                                        },
                                                                        {
                                                                            "name":"l:PIO:flush_buffer",
                                                                            "multiParent":false,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":208.0,
                                                                                "recurse":false,
                                                                                "wallClock":33.306736,
                                                                                "max":0.786214,
                                                                                "min":0.013169,
                                                                                "utrOverhead":1.7e-05
                                                                            },
                                                                            "children":[
                                                                                {
                                                                                    "name":"l:PIO:PIOc_write_darray_multi",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":208.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":33.302837,
                                                                                    "max":0.786191,
                                                                                    "min":0.013159,
                                                                                    "utrOverhead":1.7e-05
                                                                                    },
                                                                                    "children":[
                                                                                    {
                                                                                        "name":"l:PIO:rearrange_comp2io",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":208.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":12.009998,
                                                                                            "max":0.314142,
                                                                                            "min":0.008554,
                                                                                            "utrOverhead":1.7e-05
                                                                                        },
                                                                                        "children":[
                                                                                            {
                                                                                                "name":"l:PIO:pio_swapm",
                                                                                                "multiParent":true,
                                                                                                "values":{
                                                                                                "on":false,
                                                                                                "called":432.0,
                                                                                                "recurse":false,
                                                                                                "wallClock":12.705971,
                                                                                                "max":0.309958,
                                                                                                "min":0.004169,
                                                                                                "utrOverhead":3.5e-05
                                                                                                },
                                                                                                "children":[
                                                                                                
                                                                                                ]
                                                                                            }
                                                                                        ]
                                                                                    },
                                                                                    {
                                                                                        "name":"l:PIO:write_darray_multi_par",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":208.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":15.285944,
                                                                                            "max":0.391393,
                                                                                            "min":0.000363,
                                                                                            "utrOverhead":1.7e-05
                                                                                        },
                                                                                        "children":[
                                                                                            
                                                                                        ]
                                                                                    }
                                                                                    ]
                                                                                }
                                                                            ]
                                                                        }
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"l:PIO:put_att_id_int",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":1260.0,
                                                            "recurse":false,
                                                            "wallClock":0.038264,
                                                            "max":0.007388,
                                                            "min":1.5e-05,
                                                            "utrOverhead":0.000103
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l:PIO:put_att_id_real",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":9424.0,
                                                            "recurse":false,
                                                            "wallClock":0.214388,
                                                            "max":0.000537,
                                                            "min":1.4e-05,
                                                            "utrOverhead":0.000774
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"l:hist_htapes_wrapup_tconst",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":24.0,
                                                        "recurse":false,
                                                        "wallClock":0.21306,
                                                        "max":0.071784,
                                                        "min":0.005765,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"l:PIO:initdecomp_dof",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":8.0,
                                                            "recurse":false,
                                                            "wallClock":0.2362,
                                                            "max":0.036309,
                                                            "min":0.025829,
                                                            "utrOverhead":1e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l:PIO:PIOc_initdecomp",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":8.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.236168,
                                                                    "max":0.036304,
                                                                    "min":0.025827,
                                                                    "utrOverhead":1e-06
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"l:PIO:box_rearrange_create",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":8.0,
                                                                        "recurse":false,
                                                                        "wallClock":0.227804,
                                                                        "max":0.030773,
                                                                        "min":0.025643,
                                                                        "utrOverhead":1e-06
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"l:PIO:put_var_1d_double",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":150.0,
                                                            "recurse":false,
                                                            "wallClock":0.042959,
                                                            "max":0.00046,
                                                            "min":0.000245,
                                                            "utrOverhead":1.2e-05
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l:PIO:PIOc_put_vars_tc",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":474.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.077656,
                                                                    "max":0.000369,
                                                                    "min":9.5e-05,
                                                                    "utrOverhead":3.9e-05
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"l:PIO:put_vara_1d_int",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":124.0,
                                                            "recurse":false,
                                                            "wallClock":0.014369,
                                                            "max":0.000218,
                                                            "min":9.7e-05,
                                                            "utrOverhead":1e-05
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l:PIO:put_vara_1d_double",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":48.0,
                                                            "recurse":false,
                                                            "wallClock":0.005598,
                                                            "max":0.000194,
                                                            "min":9.9e-05,
                                                            "utrOverhead":4e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l:PIO:put_vara_1d_text",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":52.0,
                                                            "recurse":false,
                                                            "wallClock":0.006613,
                                                            "max":0.00022,
                                                            "min":9.9e-05,
                                                            "utrOverhead":4e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"l:PIO:write_darray_int",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":140.0,
                                                            "recurse":false,
                                                            "wallClock":0.072769,
                                                            "max":0.007796,
                                                            "min":6.9e-05,
                                                            "utrOverhead":1.1e-05
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"l:hist_htapes_wrapup_write",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":24.0,
                                                        "recurse":false,
                                                        "wallClock":2.627572,
                                                        "max":0.163304,
                                                        "min":0.103668,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"l:PIO:write_darray_double",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":4994.0,
                                                            "recurse":false,
                                                            "wallClock":1.868694,
                                                            "max":0.0013,
                                                            "min":0.000137,
                                                            "utrOverhead":0.00041
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l:PIO:PIOc_write_darray",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":5134.0,
                                                                    "recurse":false,
                                                                    "wallClock":1.929443,
                                                                    "max":0.007788,
                                                                    "min":6.6e-05,
                                                                    "utrOverhead":0.000422
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"l:elm_drv_io_wrest",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":2.0,
                                                "recurse":false,
                                                "wallClock":11.659203,
                                                "max":5.88305,
                                                "min":5.776153,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                {
                                                    "name":"l:PIO:put_att_id_int",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":1260.0,
                                                        "recurse":false,
                                                        "wallClock":0.038264,
                                                        "max":0.007388,
                                                        "min":1.5e-05,
                                                        "utrOverhead":0.000103
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"l:subgridRest_write",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":4.0,
                                                        "recurse":false,
                                                        "wallClock":0.390362,
                                                        "max":0.182575,
                                                        "min":0.065689,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"l:PIO:initdecomp_dof",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":8.0,
                                                            "recurse":false,
                                                            "wallClock":0.2362,
                                                            "max":0.036309,
                                                            "min":0.025829,
                                                            "utrOverhead":1e-06
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"l:PIO:PIOc_initdecomp",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":8.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.236168,
                                                                    "max":0.036304,
                                                                    "min":0.025827,
                                                                    "utrOverhead":1e-06
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"l:PIO:box_rearrange_create",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":8.0,
                                                                        "recurse":false,
                                                                        "wallClock":0.227804,
                                                                        "max":0.030773,
                                                                        "min":0.025643,
                                                                        "utrOverhead":1e-06
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                },
                                                {
                                                    "name":"l:PIO:put_att_id_double",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":660.0,
                                                        "recurse":false,
                                                        "wallClock":0.01424,
                                                        "max":0.000473,
                                                        "min":1.6e-05,
                                                        "utrOverhead":5.4e-05
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"l:subgridRest_write-read",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":4.0,
                                                        "recurse":false,
                                                        "wallClock":0.01807,
                                                        "max":0.006084,
                                                        "min":0.002854,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"l:PIO:put_att_1d_id_int",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":138.0,
                                                        "recurse":false,
                                                        "wallClock":0.003128,
                                                        "max":0.000394,
                                                        "min":1.6e-05,
                                                        "utrOverhead":1.1e-05
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"l:PIO:put_var_0d_int",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":68.0,
                                                        "recurse":false,
                                                        "wallClock":0.014728,
                                                        "max":0.000355,
                                                        "min":0.000128,
                                                        "utrOverhead":6e-06
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"l:PIO:put_var_1d_text",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":26.0,
                                                        "recurse":false,
                                                        "wallClock":0.009794,
                                                        "max":0.000624,
                                                        "min":0.000279,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"l:PIO:put_var_1d_int",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":4.0,
                                                        "recurse":false,
                                                        "wallClock":0.00123,
                                                        "max":0.000333,
                                                        "min":0.000283,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"l:PIO:put_var_0d_double",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":2.0,
                                                        "recurse":false,
                                                        "wallClock":0.000529,
                                                        "max":0.000281,
                                                        "min":0.000248,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            }
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"l:lc_lnd_export",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":1.413219,
                                    "max":0.000198,
                                    "min":2.9e-05,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"l:lc_elm2_adv_timestep",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":0.032171,
                                    "max":0.000145,
                                    "min":1e-06,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    
                                    ]
                                }
                            ]
                        },
                        {
                            "name":"CPL:ROF_RUN",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":5840.0,
                                "recurse":false,
                                "wallClock":4509.155762,
                                "max":2.21235,
                                "min":0.764371,
                                "utrOverhead":0.000479
                            },
                            "children":[
                                {
                                    "name":"r:lc_rof_import",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":5840.0,
                                    "recurse":false,
                                    "wallClock":29.948133,
                                    "max":0.006301,
                                    "min":0.003985,
                                    "utrOverhead":0.000479
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"r:mosartr_tot",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":5840.0,
                                    "recurse":false,
                                    "wallClock":4407.307129,
                                    "max":2.184602,
                                    "min":0.745946,
                                    "utrOverhead":0.000479
                                    },
                                    "children":[
                                    {
                                        "name":"r:mosartr_budget",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":12424.0,
                                            "recurse":false,
                                            "wallClock":51.383644,
                                            "max":0.006099,
                                            "min":0.000646,
                                            "utrOverhead":0.00102
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"r:mosartr_flood",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":2.011035,
                                            "max":0.00084,
                                            "min":0.000297,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"r:mosartr_SMdirect",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":62.819687,
                                            "max":0.015769,
                                            "min":0.008097,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"r:mosartr_subcycling",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":4125.65918,
                                            "max":0.708443,
                                            "min":0.704682,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            {
                                                "name":"r:mosartr_euler",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":17520.0,
                                                "recurse":false,
                                                "wallClock":3934.763672,
                                                "max":0.22616,
                                                "min":0.223572,
                                                "utrOverhead":0.001438
                                                },
                                                "children":[
                                                {
                                                    "name":"r:mosartr_hillslope",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":17520.0,
                                                        "recurse":false,
                                                        "wallClock":71.784348,
                                                        "max":0.00457,
                                                        "min":0.003975,
                                                        "utrOverhead":0.001438
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"r:mosartr_subnetwork",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":87600.0,
                                                        "recurse":false,
                                                        "wallClock":1243.716553,
                                                        "max":0.014769,
                                                        "min":0.014007,
                                                        "utrOverhead":0.007192
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"r:mosartr_SMeroutUp",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":87600.0,
                                                        "recurse":false,
                                                        "wallClock":384.602356,
                                                        "max":0.005869,
                                                        "min":0.0037,
                                                        "utrOverhead":0.007192
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                },
                                                {
                                                    "name":"r:mosartr_chanroute",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":87600.0,
                                                        "recurse":false,
                                                        "wallClock":2032.075073,
                                                        "max":0.023564,
                                                        "min":0.022973,
                                                        "utrOverhead":0.007192
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"r:mosartr_hbuf",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":117.239166,
                                            "max":0.021225,
                                            "min":0.018998,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"r:mosartr_htapes",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":5840.0,
                                            "recurse":false,
                                            "wallClock":10.500015,
                                            "max":0.532268,
                                            "min":5e-06,
                                            "utrOverhead":0.000479
                                        },
                                        "children":[
                                            {
                                                "name":"r:PIO:createfile",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":28.0,
                                                "recurse":false,
                                                "wallClock":1.944321,
                                                "max":0.832774,
                                                "min":0.004008,
                                                "utrOverhead":2e-06
                                                },
                                                "children":[
                                                {
                                                    "name":"r:PIO:PIOc_createfile",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":28.0,
                                                        "recurse":false,
                                                        "wallClock":1.94419,
                                                        "max":0.832769,
                                                        "min":0.004002,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:put_att_id_text",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":2948.0,
                                                "recurse":false,
                                                "wallClock":0.04016,
                                                "max":5.1e-05,
                                                "min":8e-06,
                                                "utrOverhead":0.000242
                                                },
                                                "children":[
                                                {
                                                    "name":"r:PIO:PIOc_put_att_tc",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":4182.0,
                                                        "recurse":false,
                                                        "wallClock":0.048329,
                                                        "max":4.9e-05,
                                                        "min":6e-06,
                                                        "utrOverhead":0.000343
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"r:PIO:write_total",
                                                            "multiParent":true,
                                                            "values":{
                                                            "on":false,
                                                            "called":5482.0,
                                                            "recurse":false,
                                                            "wallClock":11.830654,
                                                            "max":0.83277,
                                                            "min":4e-06,
                                                            "utrOverhead":0.00045
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"r:PIO:flush_buffer",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":74.0,
                                                                    "recurse":false,
                                                                    "wallClock":9.284684,
                                                                    "max":0.383242,
                                                                    "min":0.012668,
                                                                    "utrOverhead":6e-06
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"r:PIO:PIOc_write_darray_multi",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":74.0,
                                                                        "recurse":false,
                                                                        "wallClock":9.282966,
                                                                        "max":0.383208,
                                                                        "min":0.012654,
                                                                        "utrOverhead":6e-06
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"r:PIO:rearrange_comp2io",
                                                                            "multiParent":false,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":74.0,
                                                                                "recurse":false,
                                                                                "wallClock":7.127452,
                                                                                "max":0.304361,
                                                                                "min":0.012626,
                                                                                "utrOverhead":6e-06
                                                                            },
                                                                            "children":[
                                                                                {
                                                                                    "name":"r:PIO:pio_swapm",
                                                                                    "multiParent":true,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":80.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":7.125644,
                                                                                    "max":0.304324,
                                                                                    "min":9e-06,
                                                                                    "utrOverhead":7e-06
                                                                                    },
                                                                                    "children":[
                                                                                    
                                                                                    ]
                                                                                }
                                                                            ]
                                                                        },
                                                                        {
                                                                            "name":"r:PIO:write_darray_multi_par",
                                                                            "multiParent":false,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":74.0,
                                                                                "recurse":false,
                                                                                "wallClock":8.9e-05,
                                                                                "max":3e-06,
                                                                                "min":0.0,
                                                                                "utrOverhead":6e-06
                                                                            },
                                                                            "children":[
                                                                                
                                                                            ]
                                                                        }
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:put_att_id_real",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":1200.0,
                                                "recurse":false,
                                                "wallClock":0.016382,
                                                "max":2.7e-05,
                                                "min":1e-05,
                                                "utrOverhead":9.9e-05
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:put_vara_1d_int",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":150.0,
                                                "recurse":false,
                                                "wallClock":0.00398,
                                                "max":3.5e-05,
                                                "min":2.3e-05,
                                                "utrOverhead":1.2e-05
                                                },
                                                "children":[
                                                {
                                                    "name":"r:PIO:PIOc_put_vars_tc",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":504.0,
                                                        "recurse":false,
                                                        "wallClock":0.011771,
                                                        "max":4.3e-05,
                                                        "min":1.9e-05,
                                                        "utrOverhead":4.1e-05
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:put_vara_1d_double",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":98.0,
                                                "recurse":false,
                                                "wallClock":0.002469,
                                                "max":3.4e-05,
                                                "min":2.3e-05,
                                                "utrOverhead":8e-06
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:put_vara_1d_text",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":252.0,
                                                "recurse":false,
                                                "wallClock":0.006441,
                                                "max":4.6e-05,
                                                "min":2.3e-05,
                                                "utrOverhead":2.1e-05
                                                },
                                                "children":[
                                                {
                                                    "name":"r:PIO:PIOc_put_vars_tc",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":504.0,
                                                        "recurse":false,
                                                        "wallClock":0.011771,
                                                        "max":4.3e-05,
                                                        "min":1.9e-05,
                                                        "utrOverhead":4.1e-05
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:initdecomp_dof",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":2.0,
                                                "recurse":false,
                                                "wallClock":0.036534,
                                                "max":0.01828,
                                                "min":0.018254,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                {
                                                    "name":"r:PIO:PIOc_initdecomp",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":2.0,
                                                        "recurse":false,
                                                        "wallClock":0.036522,
                                                        "max":0.018273,
                                                        "min":0.018249,
                                                        "utrOverhead":0.0
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"r:PIO:box_rearrange_create",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":2.0,
                                                            "recurse":false,
                                                            "wallClock":0.036221,
                                                            "max":0.018151,
                                                            "min":0.01807,
                                                            "utrOverhead":0.0
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"r:PIO:pio_swapm",
                                                                "multiParent":true,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":80.0,
                                                                    "recurse":false,
                                                                    "wallClock":7.125644,
                                                                    "max":0.304324,
                                                                    "min":9e-06,
                                                                    "utrOverhead":7e-06
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:write_darray_int",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":24.0,
                                                "recurse":false,
                                                "wallClock":0.006359,
                                                "max":0.000292,
                                                "min":0.000242,
                                                "utrOverhead":2e-06
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:write_darray_double",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":716.0,
                                                "recurse":false,
                                                "wallClock":0.536314,
                                                "max":0.006721,
                                                "min":0.00027,
                                                "utrOverhead":5.9e-05
                                                },
                                                "children":[
                                                {
                                                    "name":"r:PIO:PIOc_write_darray",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":740.0,
                                                        "recurse":false,
                                                        "wallClock":0.540188,
                                                        "max":0.006709,
                                                        "min":0.00024,
                                                        "utrOverhead":6.1e-05
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:closefile",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":28.0,
                                                "recurse":false,
                                                "wallClock":9.29325,
                                                "max":0.450228,
                                                "min":0.000265,
                                                "utrOverhead":2e-06
                                                },
                                                "children":[
                                                {
                                                    "name":"r:PIO:PIOc_closefile",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":28.0,
                                                        "recurse":false,
                                                        "wallClock":9.293127,
                                                        "max":0.450223,
                                                        "min":0.000264,
                                                        "utrOverhead":2e-06
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"r:PIO:PIOc_closefile_write_mode",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":28.0,
                                                            "recurse":false,
                                                            "wallClock":9.285785,
                                                            "max":0.449945,
                                                            "min":4e-06,
                                                            "utrOverhead":2e-06
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"r:mosartr_rest",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":2.0,
                                            "recurse":false,
                                            "wallClock":2.003781,
                                            "max":1.009574,
                                            "min":0.994207,
                                            "utrOverhead":0.0
                                        },
                                        "children":[
                                            {
                                                "name":"r:PIO:put_vara_1d_text",
                                                "multiParent":true,
                                                "values":{
                                                "on":false,
                                                "called":252.0,
                                                "recurse":false,
                                                "wallClock":0.006441,
                                                "max":4.6e-05,
                                                "min":2.3e-05,
                                                "utrOverhead":2.1e-05
                                                },
                                                "children":[
                                                {
                                                    "name":"r:PIO:PIOc_put_vars_tc",
                                                    "multiParent":true,
                                                    "values":{
                                                        "on":false,
                                                        "called":504.0,
                                                        "recurse":false,
                                                        "wallClock":0.011771,
                                                        "max":4.3e-05,
                                                        "min":1.9e-05,
                                                        "utrOverhead":4.1e-05
                                                    },
                                                    "children":[
                                                        
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:put_att_1d_id_int",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":18.0,
                                                "recurse":false,
                                                "wallClock":0.00026,
                                                "max":1.5e-05,
                                                "min":1.3e-05,
                                                "utrOverhead":1e-06
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:put_att_id_int",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":16.0,
                                                "recurse":false,
                                                "wallClock":0.000225,
                                                "max":2.7e-05,
                                                "min":1.2e-05,
                                                "utrOverhead":1e-06
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"r:PIO:put_var_1d_text",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":4.0,
                                                "recurse":false,
                                                "wallClock":0.000664,
                                                "max":0.000172,
                                                "min":0.000157,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    }
                                    ]
                                },
                                {
                                    "name":"r:lc_rof_export",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":5840.0,
                                    "recurse":false,
                                    "wallClock":20.494217,
                                    "max":0.011731,
                                    "min":0.002814,
                                    "utrOverhead":0.000479
                                    },
                                    "children":[
                                    
                                    ]
                                }
                            ]
                        },
                        {
                            "name":"CPL:ATM_RUN",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":744.932251,
                                "max":0.581943,
                                "min":0.003418,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                {
                                    "name":"a:DATM_RUN",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":35040.0,
                                    "recurse":false,
                                    "wallClock":724.382263,
                                    "max":0.581384,
                                    "min":0.002853,
                                    "utrOverhead":0.002877
                                    },
                                    "children":[
                                    {
                                        "name":"a:datm_run1",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":0.414971,
                                            "max":0.000146,
                                            "min":7e-06,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    },
                                    {
                                        "name":"a:datm",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":718.788757,
                                            "max":0.581228,
                                            "min":0.002708,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            {
                                                "name":"a:datm_strdata_advance",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":641.884888,
                                                "max":0.579094,
                                                "min":0.000678,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                {
                                                    "name":"a:datm_strd_adv_total",
                                                    "multiParent":false,
                                                    "values":{
                                                        "on":false,
                                                        "called":35040.0,
                                                        "recurse":false,
                                                        "wallClock":641.820679,
                                                        "max":0.579091,
                                                        "min":0.000677,
                                                        "utrOverhead":0.002877
                                                    },
                                                    "children":[
                                                        {
                                                            "name":"a:datm_strd_adv_readLBUB",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":175200.0,
                                                            "recurse":false,
                                                            "wallClock":128.576874,
                                                            "max":0.356187,
                                                            "min":1e-06,
                                                            "utrOverhead":0.014385
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"a:datm_readLBUB_setup",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":175200.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.052013,
                                                                    "max":0.000183,
                                                                    "min":0.0,
                                                                    "utrOverhead":0.014385
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            },
                                                            {
                                                                "name":"a:datm_readLBUB_filemgt",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":175200.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.032929,
                                                                    "max":1.2e-05,
                                                                    "min":0.0,
                                                                    "utrOverhead":0.014385
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            },
                                                            {
                                                                "name":"a:datm_readLBUB_fbound",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":8786.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.052737,
                                                                    "max":1.9e-05,
                                                                    "min":1e-06,
                                                                    "utrOverhead":0.000721
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            },
                                                            {
                                                                "name":"a:datm_readLBUB_bcast",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":8786.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.353435,
                                                                    "max":0.006992,
                                                                    "min":6e-06,
                                                                    "utrOverhead":0.000721
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            },
                                                            {
                                                                "name":"a:datm_readLBUB_LB_copy",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":8786.0,
                                                                    "recurse":false,
                                                                    "wallClock":0.012997,
                                                                    "max":1.2e-05,
                                                                    "min":1e-06,
                                                                    "utrOverhead":0.000721
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            },
                                                            {
                                                                "name":"a:datm_readLBUB_UB_setup",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":8786.0,
                                                                    "recurse":false,
                                                                    "wallClock":2.750211,
                                                                    "max":0.029829,
                                                                    "min":0.000166,
                                                                    "utrOverhead":0.000721
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            },
                                                            {
                                                                "name":"a:datm_readLBUB_UB_readpio",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":8786.0,
                                                                    "recurse":false,
                                                                    "wallClock":124.929031,
                                                                    "max":0.352653,
                                                                    "min":0.001351,
                                                                    "utrOverhead":0.000721
                                                                },
                                                                "children":[
                                                                    {
                                                                        "name":"a:PIO:read_darray_1d_real",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":17856.0,
                                                                        "recurse":false,
                                                                        "wallClock":114.304214,
                                                                        "max":0.216058,
                                                                        "min":0.000302,
                                                                        "utrOverhead":0.001466
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"a:PIO:PIOc_read_darray",
                                                                            "multiParent":true,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":17858.0,
                                                                                "recurse":false,
                                                                                "wallClock":114.18251,
                                                                                "max":0.21605,
                                                                                "min":0.0003,
                                                                                "utrOverhead":0.001466
                                                                            },
                                                                            "children":[
                                                                                {
                                                                                    "name":"a:PIO:read_darray_nc_serial",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":17858.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":111.1567,
                                                                                    "max":0.215883,
                                                                                    "min":0.000231,
                                                                                    "utrOverhead":0.001466
                                                                                    },
                                                                                    "children":[
                                                                                    
                                                                                    ]
                                                                                },
                                                                                {
                                                                                    "name":"a:PIO:rearrange_io2comp",
                                                                                    "multiParent":false,
                                                                                    "values":{
                                                                                    "on":false,
                                                                                    "called":17858.0,
                                                                                    "recurse":false,
                                                                                    "wallClock":2.264022,
                                                                                    "max":0.000306,
                                                                                    "min":4.3e-05,
                                                                                    "utrOverhead":0.001466
                                                                                    },
                                                                                    "children":[
                                                                                    {
                                                                                        "name":"a:PIO:pio_swapm",
                                                                                        "multiParent":false,
                                                                                        "values":{
                                                                                            "on":false,
                                                                                            "called":17858.0,
                                                                                            "recurse":false,
                                                                                            "wallClock":2.206742,
                                                                                            "max":0.000302,
                                                                                            "min":4.1e-05,
                                                                                            "utrOverhead":0.001466
                                                                                        },
                                                                                        "children":[
                                                                                            
                                                                                        ]
                                                                                    }
                                                                                    ]
                                                                                }
                                                                            ]
                                                                        }
                                                                        ]
                                                                    },
                                                                    {
                                                                        "name":"a:PIO:closefile",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":72.0,
                                                                        "recurse":false,
                                                                        "wallClock":0.041291,
                                                                        "max":0.001341,
                                                                        "min":0.000239,
                                                                        "utrOverhead":6e-06
                                                                        },
                                                                        "children":[
                                                                        {
                                                                            "name":"a:PIO:PIOc_closefile",
                                                                            "multiParent":false,
                                                                            "values":{
                                                                                "on":false,
                                                                                "called":72.0,
                                                                                "recurse":false,
                                                                                "wallClock":0.040855,
                                                                                "max":0.001334,
                                                                                "min":0.000234,
                                                                                "utrOverhead":6e-06
                                                                            },
                                                                            "children":[
                                                                                
                                                                            ]
                                                                        }
                                                                        ]
                                                                    },
                                                                    {
                                                                        "name":"a:PIO:openfile",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":72.0,
                                                                        "recurse":false,
                                                                        "wallClock":5.649569,
                                                                        "max":0.097406,
                                                                        "min":0.058091,
                                                                        "utrOverhead":6e-06
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    },
                                                                    {
                                                                        "name":"a:PIO:read_darray_1d_double",
                                                                        "multiParent":false,
                                                                        "values":{
                                                                        "on":false,
                                                                        "called":2.0,
                                                                        "recurse":false,
                                                                        "wallClock":0.00248,
                                                                        "max":0.001246,
                                                                        "min":0.001235,
                                                                        "utrOverhead":0.0
                                                                        },
                                                                        "children":[
                                                                        
                                                                        ]
                                                                    }
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"a:datm_strd_adv_coszen",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":35040.0,
                                                            "recurse":false,
                                                            "wallClock":34.140118,
                                                            "max":0.00638,
                                                            "min":0.000466,
                                                            "utrOverhead":0.002877
                                                            },
                                                            "children":[
                                                            {
                                                                "name":"a:datm_strd_adv_coszenC",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":35040.0,
                                                                    "recurse":false,
                                                                    "wallClock":15.915809,
                                                                    "max":0.000713,
                                                                    "min":0.000406,
                                                                    "utrOverhead":0.002877
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            },
                                                            {
                                                                "name":"a:datm_strd_adv_coszenN",
                                                                "multiParent":false,
                                                                "values":{
                                                                    "on":false,
                                                                    "called":2920.0,
                                                                    "recurse":false,
                                                                    "wallClock":15.762138,
                                                                    "max":0.005834,
                                                                    "min":0.004928,
                                                                    "utrOverhead":0.00024
                                                                },
                                                                "children":[
                                                                    
                                                                ]
                                                            }
                                                            ]
                                                        },
                                                        {
                                                            "name":"a:datm_strd_adv_tint",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":140160.0,
                                                            "recurse":false,
                                                            "wallClock":7.62176,
                                                            "max":0.000447,
                                                            "min":1.8e-05,
                                                            "utrOverhead":0.011508
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"a:datm_strd_adv_fill",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":8786.0,
                                                            "recurse":false,
                                                            "wallClock":1.773971,
                                                            "max":0.000436,
                                                            "min":0.000167,
                                                            "utrOverhead":0.000721
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        },
                                                        {
                                                            "name":"a:datm_strd_adv_map",
                                                            "multiParent":false,
                                                            "values":{
                                                            "on":false,
                                                            "called":8786.0,
                                                            "recurse":false,
                                                            "wallClock":469.255676,
                                                            "max":0.074444,
                                                            "min":0.000531,
                                                            "utrOverhead":0.000721
                                                            },
                                                            "children":[
                                                            
                                                            ]
                                                        }
                                                    ]
                                                }
                                                ]
                                            },
                                            {
                                                "name":"a:datm_scatter",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":57.633736,
                                                "max":0.002233,
                                                "min":0.001514,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"a:datm_datamode",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":35040.0,
                                                "recurse":false,
                                                "wallClock":18.836601,
                                                "max":0.000882,
                                                "min":0.00048,
                                                "utrOverhead":0.002877
                                                },
                                                "children":[
                                                
                                                ]
                                            },
                                            {
                                                "name":"a:datm_restart",
                                                "multiParent":false,
                                                "values":{
                                                "on":false,
                                                "called":2.0,
                                                "recurse":false,
                                                "wallClock":0.02669,
                                                "max":0.013448,
                                                "min":0.013242,
                                                "utrOverhead":0.0
                                                },
                                                "children":[
                                                
                                                ]
                                            }
                                        ]
                                    },
                                    {
                                        "name":"a:datm_run2",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":35040.0,
                                            "recurse":false,
                                            "wallClock":5.096189,
                                            "max":0.019713,
                                            "min":1e-05,
                                            "utrOverhead":0.002877
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                }
                            ]
                        }
                        ]
                    },
                    {
                        "name":"CPL:TPROF_WRITE",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":0.29,
                        "max":0.026371,
                        "min":0.0,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        {
                            "name":"CPL:RUN_LOOP_sync1_tprf",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":13.0,
                                "recurse":false,
                                "wallClock":0.000169,
                                "max":1.6e-05,
                                "min":1.1e-05,
                                "utrOverhead":1e-06
                            },
                            "children":[
                                
                            ]
                        },
                        {
                            "name":"CPL:RUN_LOOP_t_prf",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":13.0,
                                "recurse":false,
                                "wallClock":0.285519,
                                "max":0.026337,
                                "min":0.018205,
                                "utrOverhead":1e-06
                            },
                            "children":[
                                
                            ]
                        },
                        {
                            "name":"CPL:RUN_LOOP_sync2_tprf",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":13.0,
                                "recurse":false,
                                "wallClock":0.000166,
                                "max":1.7e-05,
                                "min":1.2e-05,
                                "utrOverhead":1e-06
                            },
                            "children":[
                                
                            ]
                        }
                        ]
                    },
                    {
                        "name":"CPL:RUN_LOOP_BSTOP",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":1.0,
                        "recurse":false,
                        "wallClock":6.4e-05,
                        "max":6.4e-05,
                        "min":6.4e-05,
                        "utrOverhead":0.0
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"CPL:FINAL",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":1.0,
                        "recurse":false,
                        "wallClock":0.052023,
                        "max":0.052023,
                        "min":0.052023,
                        "utrOverhead":0.0
                        },
                        "children":[
                        {
                            "name":"CPL:cime_final",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":1.0,
                                "recurse":false,
                                "wallClock":0.052022,
                                "max":0.052022,
                                "min":0.052022,
                                "utrOverhead":0.0
                            },
                            "children":[
                                {
                                    "name":"a_f:DATM_FINAL",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":1.0,
                                    "recurse":false,
                                    "wallClock":1.3e-05,
                                    "max":1.3e-05,
                                    "min":1.3e-05,
                                    "utrOverhead":0.0
                                    },
                                    "children":[
                                    
                                    ]
                                },
                                {
                                    "name":"PIO:finalize",
                                    "multiParent":false,
                                    "values":{
                                    "on":false,
                                    "called":10.0,
                                    "recurse":false,
                                    "wallClock":0.051433,
                                    "max":0.024576,
                                    "min":0.000396,
                                    "utrOverhead":1e-06
                                    },
                                    "children":[
                                    {
                                        "name":"PIO:PIOc_finalize",
                                        "multiParent":false,
                                        "values":{
                                            "on":false,
                                            "called":10.0,
                                            "recurse":false,
                                            "wallClock":0.037202,
                                            "max":0.024248,
                                            "min":0.000189,
                                            "utrOverhead":1e-06
                                        },
                                        "children":[
                                            
                                        ]
                                    }
                                    ]
                                }
                            ]
                        }
                        ]
                    },
                    {
                        "name":"CPL:FINAL_sync1_tprf",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":1.0,
                        "recurse":false,
                        "wallClock":1.1e-05,
                        "max":1.1e-05,
                        "min":1.1e-05,
                        "utrOverhead":0.0
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"CPL:FINAL_t_prf",
                        "multiParent":false,
                        "values":{
                        "on":true,
                        "called":0.0,
                        "recurse":false,
                        "wallClock":0.0,
                        "max":0.0,
                        "min":0.0,
                        "utrOverhead":0.0
                        },
                        "children":[
                        
                        ]
                    }
                ],
                [
                    {
                        "name":"l:decomp_vert",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":0.22753,
                        "max":4.4e-05,
                        "min":2e-06,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:beggridwbal",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":5.995598,
                        "max":0.0003,
                        "min":0.00016,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:cnpinit",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":0.028849,
                        "max":2.8e-05,
                        "min":1e-06,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        {
                            "name":"l:cnpvegsumm",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":0.003854,
                                "max":1e-06,
                                "min":0.0,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        }
                        ]
                    },
                    {
                        "name":"l:begwbal",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":1.080217,
                        "max":0.00011,
                        "min":2.8e-05,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:begcnpbal",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":0.003979,
                        "max":1e-06,
                        "min":0.0,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:drvinit",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":4.676682,
                        "max":0.00024,
                        "min":7.8e-05,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:canhydro",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":10.612647,
                        "max":0.000446,
                        "min":0.000208,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:surfrad",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":22.636253,
                        "max":0.000907,
                        "min":0.00025,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:bgp1",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":9.324726,
                        "max":0.000373,
                        "min":0.000169,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:bgflux",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":26.939186,
                        "max":0.001145,
                        "min":0.000433,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:canflux",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":424.158722,
                        "max":0.023453,
                        "min":0.005931,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        {
                            "name":"l:can_iter",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":364.454529,
                                "max":0.021695,
                                "min":0.004532,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        }
                        ]
                    },
                    {
                        "name":"l:uflux",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":8.646675,
                        "max":0.000879,
                        "min":0.000143,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:bgplake",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":54.24786,
                        "max":0.002456,
                        "min":0.000985,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        {
                            "name":"l:bgc",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":33.709774,
                                "max":0.001596,
                                "min":0.000641,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        }
                        ]
                    },
                    {
                        "name":"l:soiltemperature",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":117.924889,
                        "max":0.00437,
                        "min":0.001701,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        {
                            "name":"l:SoilThermProp",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":19.871801,
                                "max":0.001259,
                                "min":0.000299,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        },
                        {
                            "name":"l:SoilTempBandDiag",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":70080.0,
                                "recurse":false,
                                "wallClock":23.190128,
                                "max":0.001324,
                                "min":7.5e-05,
                                "utrOverhead":0.005754
                            },
                            "children":[
                                
                            ]
                        },
                        {
                            "name":"l:PhaseChangeH2osfc",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":0.100251,
                                "max":0.000113,
                                "min":1e-06,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        },
                        {
                            "name":"l:PhaseChangebeta",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":7.723561,
                                "max":0.000851,
                                "min":8.8e-05,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        }
                        ]
                    },
                    {
                        "name":"l:bgp2",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":13.250068,
                        "max":0.001238,
                        "min":0.000172,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        {
                            "name":"l:bgp2_loop_1",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":1.939811,
                                "max":0.000275,
                                "min":2.4e-05,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        },
                        {
                            "name":"l:bgp2_loop_2",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":3.337143,
                                "max":0.00048,
                                "min":3.4e-05,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        },
                        {
                            "name":"l:bgp2_loop_3",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":6.308725,
                                "max":0.000741,
                                "min":8.9e-05,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        },
                        {
                            "name":"l:bgp2_loop_4",
                            "multiParent":false,
                            "values":{
                                "on":false,
                                "called":35040.0,
                                "recurse":false,
                                "wallClock":1.295328,
                                "max":0.000221,
                                "min":1.9e-05,
                                "utrOverhead":0.002877
                            },
                            "children":[
                                
                            ]
                        }
                        ]
                    },
                    {
                        "name":"l:patch2col",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":6.99819,
                        "max":0.00079,
                        "min":0.000116,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:hydro without drainage",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":66.278023,
                        "max":0.002847,
                        "min":0.001177,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:hylake",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":5.080859,
                        "max":0.000781,
                        "min":6.9e-05,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:snow_init",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":2.462377,
                        "max":0.00036,
                        "min":3.5e-05,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:ecosysdyn",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":1.911502,
                        "max":0.000316,
                        "min":2.3e-05,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:depvel",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":70080.0,
                        "recurse":false,
                        "wallClock":0.042217,
                        "max":3e-05,
                        "min":0.0,
                        "utrOverhead":0.005754
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:hydro2 drainage",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":5.379766,
                        "max":0.000751,
                        "min":9e-05,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:balchk",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":4.440455,
                        "max":0.000654,
                        "min":8.1e-05,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:gridbalchk",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":4.228576,
                        "max":0.000743,
                        "min":7.5e-05,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:surfalb",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":47.534462,
                        "max":0.003185,
                        "min":0.000553,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    },
                    {
                        "name":"l:urbsurfalb",
                        "multiParent":false,
                        "values":{
                        "on":false,
                        "called":35040.0,
                        "recurse":false,
                        "wallClock":11.193721,
                        "max":0.001022,
                        "min":0.000176,
                        "utrOverhead":0.002877
                        },
                        "children":[
                        
                        ]
                    }
                ]
            ],
            "meta":{
                "expid":"114392",
                "rank":"0",
                "compset":"ICRUELM",
                "res":"r0125_r0125_oRRS18to6v3"
            }
        }

    **Query parameters**
            * ``expID (int)``: experiment id value
            * ``rank (int)``: rank of the experiment

    .. note::

       note

.. envvar:: /svg/runtime/<int:expid>

    Get a specific list of elements from e3smexp

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/svg/runtime/<int:expid>

    **Example response**:

    .. sourcecode:: text

        image of runtime 

    **Query parameters**
            * ``expid (int)``: experiment id value

    .. note::

       note

.. envvar:: /xmlviewer/<int:mexpid>/<mname>

    Get xml view stats page

    **Example request**:

    .. tabs::

        .. code-tab:: bash

            $ curl https://pace.ornl.gov/xmlviewer/<int:mexpid>/<mname>

    **Example response**:

    .. sourcecode:: json

        {
            "file":{
                "@id":"env_archive.xml",
                "@version":"2.0",
                "header":"These are the variables specific to the short term archiver.\n      See  ./case.st_archive --help for details on running the short term archiver script.\n      To validate the env_archive.xml file using xmllint, run\n      xmllint -schema $SRCROOT/cime/config/xml_schemas/env_archive.xsd env_archive.xml\n      from the case root.\n      The patterns below are Python regular expressions.\n      The file names created from these patterns will add an optional digit\n      to them and will enclose them in a pair of '.'.\n      Some useful Python metacharacters are:\n         [] = any single character inside the brackets\n         \\d = a digit = [0123456789] = [0-9]\n          ? = 0 or 1 of the previous character\n          * = 0 or more of the previous character (greedy!)\n          + = 1 or more of the previous character (greedy!)\n         \\. = a period\n          . = any non-newline character\n      Use them carefully.  They're often confused with shell-type\n      wild card characters.",
                "components":{
                    "@version":"2.0",
                    "comp_archive_spec":[
                        {
                        "@compclass":"atm",
                        "@compname":"cam",
                        "rest_file_extension":[
                            "[ri]",
                            "rh\\d*",
                            "rs"
                        ],
                        "hist_file_extension":[
                            "h\\d*.*\\.nc$",
                            "e"
                        ],
                        "rest_history_varname":"nhfil",
                        "rpointer":{
                            "rpointer_file":"rpointer.atm$NINST_STRING",
                            "rpointer_content":"$CASE.cam$NINST_STRING.r.$DATENAME.nc"
                        },
                        "test_file_names":{
                            "tfile":[
                                {
                                    "@disposition":"copy",
                                    "#text":"rpointer.atm"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"rpointer.atm_9999"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"casename.cam.r.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"casename.cam.rh4.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"move",
                                    "#text":"casename.cam.h0.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"ignore",
                                    "#text":"casename.cam.h0.1976-01-01-00000.nc.base"
                                },
                                {
                                    "@disposition":"move",
                                    "#text":"casename.cam_0002.e.postassim.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"move",
                                    "#text":"casename.cam_0002.e.preassim.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"casename.cam.i.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"ignore",
                                    "#text":"anothercasename.cam.i.1976-01-01-00000.nc"
                                }
                            ]
                        }
                        },
                        {
                        "@compclass":"lnd",
                        "@compname":"clm",
                        "rest_file_extension":[
                            "r",
                            "rh\\d?"
                        ],
                        "hist_file_extension":[
                            "h\\d*.*\\.nc$",
                            "e"
                        ],
                        "rest_history_varname":"locfnh",
                        "rpointer":{
                            "rpointer_file":"rpointer.lnd$NINST_STRING",
                            "rpointer_content":"./$CASE.clm2$NINST_STRING.r.$DATENAME.nc"
                        },
                        "test_file_names":{
                            "tfile":[
                                {
                                    "@disposition":"copy",
                                    "#text":"rpointer.lnd"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"rpointer.lnd_9999"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"casename.clm2.r.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"casename.clm2.rh4.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"move",
                                    "#text":"casename.clm2.h0.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"ignore",
                                    "#text":"casename.clm2.h0.1976-01-01-00000.nc.base"
                                },
                                {
                                    "@disposition":"move",
                                    "#text":"casename.clm2_0002.e.postassim.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"move",
                                    "#text":"casename.clm2_0002.e.preassim.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"ignore",
                                    "#text":"anothercasename.clm2.i.1976-01-01-00000.nc"
                                }
                            ]
                        }
                        },
                        {
                        "@compclass":"ice",
                        "@compname":"cice",
                        "rest_file_extension":"[ri]",
                        "hist_file_extension":"h\\d*",
                        "rest_history_varname":"unset",
                        "rpointer":{
                            "rpointer_file":"rpointer.ice$NINST_STRING",
                            "rpointer_content":"./$CASE.cice$NINST_STRING.r.$DATENAME.nc"
                        },
                        "test_file_names":{
                            "tfile":[
                                {
                                    "@disposition":"copy",
                                    "#text":"rpointer.ice"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"casename.cice.r.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"move",
                                    "#text":"casename.cice.h.1976-01-01-00000.nc"
                                }
                            ]
                        }
                        },
                        {
                        "@compclass":"ocn",
                        "@compname":"docn",
                        "rest_file_extension":"rs*\\d*",
                        "rest_history_varname":"unset",
                        "rpointer":{
                            "rpointer_file":"rpointer.ocn$NINST_STRING",
                            "rpointer_content":"$CASE.docn$NINST_STRING.r.$DATENAME.nc,$CASE.docn$NINST_STRING.rs1.$DATENAME.bin"
                        }
                        },
                        {
                        "@compclass":"cpl",
                        "@compname":"drv",
                        "rest_file_extension":"r",
                        "hist_file_extension":"hi?\\d*.*\\.nc$",
                        "rest_history_varname":"unset",
                        "rpointer":{
                            "rpointer_file":"rpointer$NINST_STRING.drv",
                            "rpointer_content":"$CASE.cpl$NINST_STRING.r.$DATENAME.nc"
                        },
                        "test_file_names":{
                            "tfile":[
                                {
                                    "@disposition":"move",
                                    "#text":"cpl_0001.log.5548574.chadmin1.180228-124723.gz"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"casename.cpl.r.1976-01-01-00000.nc"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"rpointer.drv_0001"
                                },
                                {
                                    "@disposition":"copy",
                                    "#text":"rpointer.drv"
                                },
                                {
                                    "@disposition":"ignore",
                                    "#text":"casenamenot.cpl.r.1976-01-01-00000.nc"
                                }
                            ]
                        }
                        }
                    ]
                }
            }
        }

    **Query parameters**
            * ``mexpid (int)``: experiment id value
            * ``mname (string)``: XML filename 

    .. note::

       note

