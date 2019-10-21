# SPDX-License-Identifier: GPL-2.0
#
# Makefile for Kernel-based Virtual Machine module, HYP part
#

ccflags-y += -fno-stack-protector -DDISABLE_BRANCH_PROFILING \
		$(DISABLE_STACKLEAK_PLUGIN)

KVM=../../../../virt/kvm

obj-y += $(KVM)/arm/hyp/vgic-v3-sr.o
obj-y += $(KVM)/arm/hyp/timer-sr.o
obj-y += $(KVM)/arm/hyp/aarch32.o

obj-y += vgic-v2-cpuif-proxy.o
obj-y += sysreg-sr.o
obj-y += debug-sr.o
obj-y += entry.o
obj-y += switch.o
obj-y += fpsimd.o
obj-y += tlb.o
obj-y += hyp-entry.o

# KVM code is run at a different exception code with a different map, so
# compiler instrumentation that inserts callbacks or checks into the code may
# cause crashes. Just disable it.
GCOV_PROFILE	:= n
KASAN_SANITIZE	:= n
UBSAN_SANITIZE	:= n
KCOV_INSTRUMENT	:= n
