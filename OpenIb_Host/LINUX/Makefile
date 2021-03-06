# BEGIN_ICS_COPYRIGHT8 ****************************************
# 
# Copyright (c) 2015, Intel Corporation
# 
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are met:
# 
#     * Redistributions of source code must retain the above copyright notice,
#       this list of conditions and the following disclaimer.
#     * Redistributions in binary form must reproduce the above copyright
#       notice, this list of conditions and the following disclaimer in the
#       documentation and/or other materials provided with the distribution.
#     * Neither the name of Intel Corporation nor the names of its contributors
#       may be used to endorse or promote products derived from this software
#       without specific prior written permission.
# 
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
# AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
# IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
# DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE
# FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
# DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
# SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
# CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
# OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
# OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
# 
# END_ICS_COPYRIGHT8   ****************************************
# Makefile for LINUX

# Include Make Control Settings
include $(TL_DIR)/$(PROJ_FILE_DIR)/Makesettings.project

#=============================================================================#
# Definitions:
#-----------------------------------------------------------------------------#

# Name of SubProjects
DS_SUBPROJECTS	= 
# name of executable or downloadable image
EXECUTABLE		= #LINUX$(EXE_SUFFIX)
# list of sub directories to build
DIRS			= 
# C files (.c)
CFILES			= \
				# Add more c files here
# C++ files (.cpp)
CCFILES			= \
				# Add more cpp files here
# lex files (.lex)
LFILES			= \
				# Add more lex files here
# archive library files (basename, $ARFILES will add MOD_LIB_DIR/prefix and suffix)
LIBFILES = 
# Windows Resource Files (.rc)
RSCFILES		=
# Windows IDL File (.idl)
IDLFILE			=
# Windows Linker Module Definitions (.def) file for dll's
DEFFILE			=
# targets to build during INCLUDES phase (add public includes here)
INCLUDE_TARGETS	= \
				# Add more h hpp files here
# Non-compiled files
MISC_FILES		=  \
				README \
				# Add more files here
# all source files
SOURCES			= $(CFILES) $(CCFILES) $(LFILES) $(RSCFILES) $(IDLFILE)
INSTALL_SOURCES= \
				 $(TL_DIR)/CommonInstall/util_init.pl \
				 $(TL_DIR)/CommonInstall/util_basicio.pl \
				 $(TL_DIR)/CommonInstall/util_basicfile.pl \
				 $(TL_DIR)/CommonInstall/util_configfile.pl \
				 $(TL_DIR)/CommonInstall/util_startup.pl \
				 $(TL_DIR)/CommonInstall/util_driver.pl \
				 $(TL_DIR)/CommonInstall/util_components.pl \
				 $(TL_DIR)/CommonInstall/util_blacklist.pl \
				 $(TL_DIR)/CommonInstall/util_ifcfg.pl \
				 $(TL_DIR)/CommonInstall/util_linuxconfig.pl \
				 $(TL_DIR)/CommonInstall/util_hosttools.pl \
				 $(TL_DIR)/CommonInstall/util_rpm.pl \
				 $(TL_DIR)/CommonInstall/util_build.pl \
				 $(TL_DIR)/CommonInstall/ofed_firmware.pl \
				 $(TL_DIR)/CommonInstall/comp_oftools.pl \
				 $(TL_DIR)/CommonInstall/comp_fastfabric.pl \
				 $(TL_DIR)/CommonInstall/overrides_ff.pl \
				 $(TL_DIR)/CommonInstall/main_omnipathwrap_delta.pl

ifeq "$(BUILD_TARGET_OS_VENDOR_VERSION)" "ES72"
	PREREQ_SOURCE= $(TL_DIR)/CommonInstall/comp_ff_of_prereq_RHEL72.pl
endif
ifeq "$(BUILD_TARGET_OS_VENDOR_VERSION)" "ES73"
        PREREQ_SOURCE= $(TL_DIR)/CommonInstall/comp_ff_of_prereq_RHEL73.pl
endif
ifeq "$(BUILD_TARGET_OS_VENDOR_VERSION)" "ES74"
        PREREQ_SOURCE= $(TL_DIR)/CommonInstall/comp_ff_of_prereq_RHEL74.pl
endif
ifeq "$(BUILD_TARGET_OS_VENDOR_VERSION)" "ES121"
        PREREQ_SOURCE= $(TL_DIR)/CommonInstall/comp_ff_of_prereq_SLES121.pl
endif
ifeq "$(BUILD_TARGET_OS_VENDOR_VERSION)" "ES122"
        PREREQ_SOURCE= $(TL_DIR)/CommonInstall/comp_ff_of_prereq_SLES122.pl
endif
ifeq "$(BUILD_TARGET_OS_VENDOR_VERSION)" "ES123"
        PREREQ_SOURCE= $(TL_DIR)/CommonInstall/comp_ff_of_prereq_SLES123.pl
endif

COMP_SOURCES= \
				 $(TL_DIR)/CommonInstall/comp_oftools.pl \
				 $(TL_DIR)/CommonInstall/comp_fastfabric.pl
# Source files to include in DSP File
DSP_SOURCES		= $(INCLUDE_TARGETS) $(SOURCES) $(MISC_FILES) \
				  $(RSCFILES) $(DEFFILE) $(MAKEFILE) 
# all object files
OBJECTS			= $(CFILES:.c=$(OBJ_SUFFIX)) $(CCFILES:.cpp=$(OBJ_SUFFIX)) \
				  $(LFILES:.lex=$(OBJ_SUFFIX))
RSCOBJECTS		= $(RSCFILES:.rc=$(RES_SUFFIX))
# targets to build during LIBS phase
LIB_TARGETS_IMPLIB	=
LIB_TARGETS_ARLIB	= # $(LIB_PREFIX)LINUX$(ARLIB_SUFFIX)
LIB_TARGETS_EXP		= $(LIB_TARGETS_IMPLIB:$(ARLIB_SUFFIX)=$(EXP_SUFFIX))
LIB_TARGETS_MISC	= 
# targets to build during CMDS phase
CMD_TARGETS_SHLIB	= 
CMD_TARGETS_EXE		= $(EXECUTABLE)
CMD_TARGETS_MISC	= opacapture INSTALL.pl comp.pl
# files to remove during clean phase
CLEAN_TARGETS_MISC	=  
CLEAN_TARGETS		= $(OBJECTS) $(RSCOBJECTS) $(IDL_TARGETS) $(CLEAN_TARGETS_MISC)
# other files to remove during clobber phase
CLOBBER_TARGETS_MISC= 
# sub-directory to install to within bin
BIN_SUBDIR		= 
# sub-directory to install to within include
INCLUDE_SUBDIR		=

# Additional Settings
#CLOCALDEBUG	= User defined C debugging compilation flags [Empty]
#CCLOCALDEBUG	= User defined C++ debugging compilation flags [Empty]
#CLOCAL	= User defined C flags for compiling [Empty]
#CCLOCAL	= User defined C++ flags for compiling [Empty]
#BSCLOCAL	= User flags for Browse File Builder [Empty]
#DEPENDLOCAL	= user defined makedepend flags [Empty]
#LINTLOCAL	= User defined lint flags [Empty]
#LOCAL_INCLUDE_DIRS	= User include directories to search for C/C++ headers [Empty]
#LDLOCAL	= User defined C flags for linking [Empty]
#IMPLIBLOCAL	= User flags for Object Lirary Manager [Empty]
#MIDLLOCAL	= User flags for IDL compiler [Empty]
#RSCLOCAL	= User flags for resource compiler [Empty]
#LOCALDEPLIBS	= User libraries to include in dependencies [Empty]
#LOCALLIBS		= User libraries to use when linking [Empty]
#				(in addition to LOCALDEPLIBS)
#LOCAL_LIB_DIRS	= User library directories for libpaths [Empty]

LOCALDEPLIBS = 

# Include Make Rules definitions and rules
include $(TL_DIR)/$(PROJ_FILE_DIR)/Makerules.project

#=============================================================================#
# Overrides:
#-----------------------------------------------------------------------------#
#CCOPT			=	# C++ optimization flags, default lets build config decide
#COPT			=	# C optimization flags, default lets build config decide
#SUBSYSTEM = Subsystem to build for (none, console or windows) [none]
#					 (Windows Only)
#USEMFC	= How Windows MFC should be used (none, static, shared, no_mfc) [none]
#				(Windows Only)
#=============================================================================#

#=============================================================================#
# Rules:
#-----------------------------------------------------------------------------#
# process Sub-directories
include $(TL_DIR)/Makerules/Maketargets.toplevel

# build cmds and libs
include $(TL_DIR)/Makerules/Maketargets.build

# install for includes, libs and cmds phases
include $(TL_DIR)/Makerules/Maketargets.install

# to avoid conflicts with the INSTALL pseudo target in make system build as .pl
# and rename during STAGE
INSTALL.pl: $(INSTALL_SOURCES)
	cat $(INSTALL_SOURCES) > INSTALL.pl
	chmod +x INSTALL.pl

comp.pl:
	cat $(PREREQ_SOURCE) $(COMP_SOURCES) > comp.pl
	chmod +x comp.pl
	cp comp.pl $(TL_DIR)/OpenIb_Host/.comp_fastfabric.pl
	cp comp.pl $(TL_DIR)/OpenIb_Host/.comp_oftools.pl

# install for stage phase
#include $(TL_DIR)/Makerules/Maketargets.stage
STAGE:
	$(VS)$(STAGE_INSTALL) $(STAGE_INSTALL_DIR_OPT) $(PROJ_STAGE_DIR) INSTALL.pl
	cd $(PROJ_STAGE_DIR) ; mv INSTALL.pl INSTALL
	$(VS)$(STAGE_INSTALL) $(STAGE_INSTALL_DIR_OPT) $(PROJ_STAGE_DIR) comp.pl
	$(VS)$(STAGE_INSTALL) $(STAGE_INSTALL_DIR_OPT) $(PROJ_STAGE_DIR) README
	$(VS)$(STAGE_INSTALL) $(STAGE_INSTALL_DIR_OPT) $(PROJ_STAGE_BIN_DIR) opacapture
	
# TBD - should build an rpm here
# can't use STAGE_SUB_DIR since RELEASE_TAG may not be set and it is used to
# put version suffix on STAGE_SUB_DIR
# TBD - make this a script, the wildcards for IntelOPA-Tools.* are a problem
# packaging should be filelist based, especially for release media which will
# be a subset of things found in stage
# TBD - make some of these "make variables" so this can be a simple sequence
# of commands and make will test exit codes for us
package:
	mkdir -p $(RELEASE_DIR)
	rm -f packaged_files dist_files
	cd $(STAGE_DIR) ; \
	dir=`echo IntelOPA-Tools-FF.*`; \
	ver=`expr IntelOPA-Tools-FF.* : 'IntelOPA-Tools-FF.\(.*\)$$'`; \
	rm -rf $(RELEASE_DIR)/IntelOPA-Tools-FF.$$ver ; \
	mkdir -p $(RELEASE_DIR)/IntelOPA-Tools-FF.$$ver ; \
	cp -r $$dir/arch $$dir/distro $$dir/distro_version $$dir/os_id $(RELEASE_DIR)/IntelOPA-Tools-FF.$$ver 2>/dev/null; \
	cp -r $$dir/INSTALL $$dir/comp.pl $$dir/README $$dir/version $(RELEASE_DIR)/IntelOPA-Tools-FF.$$ver ; \
	cp -r $$dir/Lsf $(RELEASE_DIR)/IntelOPA-Tools-FF.$$ver 2>/dev/null; \
	cp -r $$dir/Moab $(RELEASE_DIR)/IntelOPA-Tools-FF.$$ver 2>/dev/null; \
	echo "$(RELEASE_DIR)/IntelOPA-Tools-FF.$$ver.tgz" >> $(TL_DIR)/packaged_files; \
	echo "$(RELEASE_DIR)/IntelOPA-Tools-FF.$$ver.tgz" >> $(TL_DIR)/dist_files; \
	echo "$(RELEASE_DIR)/IntelOPA-Tools.$$ver.tgz" >> $(TL_DIR)/packaged_files; \
	echo "$(RELEASE_DIR)/IntelOPA-Tools.$$ver.tgz" >> $(TL_DIR)/dist_files; \

# TBD - make some of these "make variables" so this can be a simple sequence
# of commands and make will test exit codes for us
final_package:
	cd $(TL_DIR)/rpmbuild; \
	dir=`grep 'IntelOPA-Tools-FF\.' BUILD/opa-$${MKRPM_VER}/packaged_files |xargs dirname`; \
	filename=`grep 'IntelOPA-Tools-FF\.' BUILD/opa-$${MKRPM_VER}/packaged_files|xargs basename`; \
	subdir=$${filename%.tgz}; \
	srpmdir=$$dir/$$subdir/SRPMS; \
	basicdir=`grep 'IntelOPA-Tools\.' BUILD/opa-$${MKRPM_VER}/packaged_files |xargs dirname`; \
	basic=`grep 'IntelOPA-Tools\.' BUILD/opa-$${MKRPM_VER}/packaged_files|xargs basename`; \
	arch=`echo $(BUILD_TARGET) | tr '[A-Z]' '[a-z]'`; \
	rpmdir=$$dir/$$subdir/RPMS/$$arch;\
	basicrpmdir=$$basicdir/$${basic%.tgz}/RPMS/$$arch;\
	basicsrpmdir=$$basicdir/$${basic%.tgz}/SRPMS;\
	mkdir -p $$srpmdir; if [ $$? -ne 0 ]; then echo "ERR""OR: mkdir $$srpmdir."; fi; \
	mkdir -p $$rpmdir; if [ $$? -ne 0 ]; then echo "ERR""OR: mkdir $$rpmdir."; fi; \
	rm -rf $${basicdir}/$${basic} $${basicdir}/$${basic%.tgz}; \
	cp -rp $${dir}/$${subdir} $${basicdir}/$${basic%.tgz}; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $${basicdir}/$${basic%.tgz}."; fi; \
	cp SRPMS/opa-mpi-apps-$${MKRPM_VER}-$${MKRPM_REL}.src.rpm $$srpmdir/ ; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$srpmdir."; fi; \
	cp SRPMS/opa-$${MKRPM_VER}-$${MKRPM_REL}.src.rpm $$srpmdir/ ; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$srpmdir."; fi; \
	cp SRPMS/opa-$${MKRPM_VER}-$${MKRPM_REL}.src.rpm $$basicsrpmdir/ ; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$srpmdir."; fi; \
	cp RPMS/$$arch/opa-basic-tools-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$rpmdir."; fi; \
	cp RPMS/$$arch/opa-address-resolution-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$rpmdir."; fi; \
	cp RPMS/$$arch/opa-libopamgt-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$rpmdir."; fi; \
	cp RPMS/$$arch/opa-libopamgt-devel-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$rpmdir."; fi; \
	cp RPMS/$$arch/opa-fastfabric-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$rpmdir."; fi; \
	cp RPMS/$$arch/opa-basic-tools-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$basicrpmdir/; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$basicrpmdir."; fi; \
	cp RPMS/$$arch/opa-address-resolution-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$basicrpmdir/; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$basicrpmdir."; fi; \
	cp RPMS/$$arch/opa-libopamgt-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$basicrpmdir/; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$basicrpmdir."; fi; \
	cp RPMS/$$arch/opa-libopamgt-devel-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$basicrpmdir/; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$basicrpmdir."; fi; \
	cp RPMS/$$arch/opa-mpi-apps-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/; if [ $$? -ne 0 ]; then echo "ERR""OR: cp $$rpmdir."; fi; \
	if [ "$(BUILD_TARGET_OS_VENDOR)" = "redhat" ]; then \
		cp RPMS/$$arch/opa-debuginfo-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/;  \
	fi; \
	if [ "$(BUILD_TARGET_OS_VENDOR)" = "SuSE" ]; then \
		cp RPMS/$$arch/opa-debugsource-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/;  \
		cp RPMS/$$arch/opa-basic-tools-debuginfo-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/;  \
		cp RPMS/$$arch/opa-basic-tools-debuginfo-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$basicrpmdir/;  \
		cp RPMS/$$arch/opa-address-resolution-debuginfo-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/;  \
		cp RPMS/$$arch/opa-address-resolution-debuginfo-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$basicrpmdir/;  \
		cp RPMS/$$arch/opa-fastfabric-debuginfo-$${MKRPM_VER}-$${MKRPM_REL}.$$arch.rpm $$rpmdir/;  \
	fi; \
	cd $$dir; \
	echo "Packaging $$dir/$$filename ..."; \
	tar cvfz $$filename $$subdir; \
	echo "Packaging $$basicdir/$$basic ..."; \
	tar cvfz $${basic} --exclude mpi --exclude shmem $${basic%.tgz}
	cp $(TL_DIR)/rpmbuild/BUILD/opa-$${MKRPM_VER}/packaged_files $(TL_DIR)/$(PROJ_FILE_DIR)
	cp $(TL_DIR)/rpmbuild/BUILD/opa-$${MKRPM_VER}/dist_files $(TL_DIR)/$(PROJ_FILE_DIR)

# Unit test execution
#include $(TL_DIR)/Makerules/Maketargets.runtest

# Unit test execution
#include $(TL_DIR)/Makerules/Maketargets.runtest

#=============================================================================#

#=============================================================================#
# DO NOT DELETE THIS LINE -- make depend depends on it.
#=============================================================================#
