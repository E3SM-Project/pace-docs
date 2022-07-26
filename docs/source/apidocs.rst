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
