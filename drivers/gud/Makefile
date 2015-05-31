#
# Makefile for the kernel mobicore drivers
#
GUD_ROOT_FOLDER := drivers/gud
# add our modules to kernel.
obj-$(CONFIG_MOBICORE_API) += mcKernelApi.o
obj-$(CONFIG_MOBICORE_SUPPORT) += mcDrvModule.o

mcdrvmodule-objs := mobicore_driver/logging.o \
		MobicoreDriver/ops.o \
		MobicoreDriver/mem.o \
		MobicoreDriver/api.o \
		MobicoreDriver/main.o \
		MobicoreDriver/pm.o

mckernelapi-objs := MobicoreKernelApi/main.o \
		MobicoreKernelApi/clientlib.o \
		MobicoreKernelApi/device.o \
		MobicoreKernelApi/session.o \
		MobicoreKernelApi/connection.o

# Release mode by default
ccflags-y := -DNDEBUG -include $(GUD_ROOT_FOLDER)/build_tag.h
ccflags-y += -Wno-declaration-after-statement

ccflags-$(CONFIG_MOBICORE_DEBUG) += -DDEBUG
ccflags-$(CONFIG_MOBICORE_VERBOSE) += -DDEBUG_VERBOSE

# Use the available platform folder
ccflags-y += -I$(GUD_ROOT_FOLDER)/mobicore_driver/platforms/EXYNOS_4X12_STD

# MobiCore Driver includes
ccflags-y += -I$(GUD_ROOT_FOLDER)/MobicoreDriver/public
# MobiCore KernelApi required includes
ccflags-y += -I$(GUD_ROOT_FOLDER)/MobicoreKernelApi/include
