---
title: "Модуль virtualization"
---

Модуль позволяет управлять виртуальными машинами с помощью Kubernetes. Базируется на проекте [KubeVirt](https://github.com/kubevirt/kubevirt).

Для работы виртуальных машин используется стек QEMU (KVM) + libvirtd и CNI Cilium (необходим включенный модуль [cni-cilium](../021-cni-cilium/)). Модуль поддерживает работу с платформами хранения данных [LINSTOR](../041-linstor) или [Ceph](../031-ceph-csi/). Возможны и другие варианты хранилища.

Основные преимущества модуля:
- Простой и понятный интерфейс для работы с виртуальными машинами как с [примитивами Kubernetes](cr.html) (работать с виртуальными машинами так же легко, как с Pod'ами);
- Высокая производительность сетевого взаимодействия за счет использования CNI Сilium с поддержкой [MacVTap](https://github.com/kvaps/community/blob/macvtap-mode-for-pod-networking/design-proposals/macvtap-mode-for-pod-networking/macvtap-mode-for-pod-networking.md) (исключает накладные расходы на трансляцию адресов).
