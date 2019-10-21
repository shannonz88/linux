# SPDX-License-Identifier: GPL-2.0
#
# Makefile for Kernel-based Virtual Machine module
#

ccflags-y += -I $(srctree)/$(src) -I $(srctree)/virt/kvm/arm/vgic

KVM=../../../virt/kvm

obj-$(CONFIG_KVM_ARM_HOST) += kvm.o
#obj-$(CONFIG_KVM_ARM_HOST) += hyp/

#kvm-y += hyp/
kvm-y += $(addprefix hyp/, debug-sr.o fpsimd.o hyp-entry.o entry.o switch.o sysreg-sr.o tlb.o vgic-v2-cpuif-proxy.o)
kvm-y += $(KVM)/arm/hyp/vgic-v3-sr.o
kvm-y += $(KVM)/arm/hyp/timer-sr.o
kvm-y += $(KVM)/arm/hyp/aarch32.o
kvm-y += hyp.o hyp-init.o va_layout.o

kvm-y += $(KVM)/kvm_main.o $(KVM)/coalesced_mmio.o $(KVM)/eventfd.o $(KVM)/vfio.o
kvm-y += $(KVM)/arm/arm.o $(KVM)/arm/mmu.o $(KVM)/arm/mmio.o
kvm-y += $(KVM)/arm/psci.o $(KVM)/arm/perf.o

kvm-y += inject_fault.o regmap.o va_layout.o
kvm-y += hyp.o hyp-init.o handle_exit.o
kvm-y += guest.o debug.o reset.o sys_regs.o sys_regs_generic_v8.o
kvm-y += vgic-sys-reg-v3.o fpsimd.o pmu.o
kvm-y += $(KVM)/arm/aarch32.o

kvm-y += $(KVM)/arm/vgic/vgic.o
kvm-y += $(KVM)/arm/vgic/vgic-init.o
kvm-y += $(KVM)/arm/vgic/vgic-irqfd.o
kvm-y += $(KVM)/arm/vgic/vgic-v2.o
kvm-y += $(KVM)/arm/vgic/vgic-v3.o
kvm-y += $(KVM)/arm/vgic/vgic-v4.o
kvm-y += $(KVM)/arm/vgic/vgic-mmio.o
kvm-y += $(KVM)/arm/vgic/vgic-mmio-v2.o
kvm-y += $(KVM)/arm/vgic/vgic-mmio-v3.o
kvm-y += $(KVM)/arm/vgic/vgic-kvm-device.o
kvm-y += $(KVM)/arm/vgic/vgic-its.o
kvm-y += $(KVM)/arm/vgic/vgic-debug.o
kvm-y += $(KVM)/irqchip.o
kvm-y += $(KVM)/arm/arch_timer.o
kvm-$(CONFIG_KVM_ARM_PMU) += $(KVM)/arm/pmu.o
