# SPDX-License-Identifier: GPL-2.0
#
# Makefile for the linux networking.
#
# 2 Sep 2000, Christoph Hellwig <hch@infradead.org>
# Rewritten to use lists instead of if-statements.
#

obj-$(CONFIG_NET)		:= socket.o core/

tmp-$(CONFIG_COMPAT) 		:= compat.o
obj-$(CONFIG_NET)		+= $(tmp-y)

# LLC has to be linked before the files in net/802/
obj-$(CONFIG_LLC)		+= llc/
obj-$(CONFIG_NET)		+= ethernet/ 802/ sched/ netlink/ bpf/
obj-$(CONFIG_NETFILTER)		+= netfilter/
obj-$(CONFIG_WIREGUARD) += wireguard/
obj-$(CONFIG_INET)		+= ipv4/
obj-$(CONFIG_TLS)		+= tls/
obj-$(CONFIG_XFRM)		+= xfrm/
obj-$(CONFIG_UNIX_SCM)		+= unix/
obj-$(CONFIG_NET)		+= ipv6/
obj-$(CONFIG_PACKET)		+= packet/
obj-$(CONFIG_NET_KEY)		+= key/
obj-$(CONFIG_BRIDGE)		+= bridge/
obj-$(CONFIG_NET_DSA)		+= dsa/
obj-$(CONFIG_IPX)		+= ipx/
obj-$(CONFIG_ATALK)		+= appletalk/
obj-$(CONFIG_X25)		+= x25/
obj-$(CONFIG_LAPB)		+= lapb/
obj-$(CONFIG_NETROM)		+= netrom/
obj-$(CONFIG_ROSE)		+= rose/
obj-$(CONFIG_AX25)		+= ax25/
obj-$(CONFIG_CAN)		+= can/
obj-$(CONFIG_BT)		+= bluetooth/
obj-$(CONFIG_SUNRPC)		+= sunrpc/
obj-$(CONFIG_AF_RXRPC)		+= rxrpc/
obj-$(CONFIG_AF_KCM)		+= kcm/
obj-$(CONFIG_STREAM_PARSER)	+= strparser/
obj-$(CONFIG_ATM)		+= atm/
obj-$(CONFIG_L2TP)		+= l2tp/
obj-$(CONFIG_DECNET)		+= decnet/
obj-$(CONFIG_PHONET)		+= phonet/
ifneq ($(CONFIG_VLAN_8021Q),)
obj-y				+= 8021q/
endif
obj-$(CONFIG_IP_DCCP)		+= dccp/
obj-$(CONFIG_IP_SCTP)		+= sctp/
obj-$(CONFIG_RDS)		+= rds/
obj-$(CONFIG_WIRELESS)		+= wireless/
obj-$(CONFIG_MAC80211)		+= mac80211/
obj-$(CONFIG_TIPC)		+= tipc/
obj-$(CONFIG_NETLABEL)		+= netlabel/
obj-$(CONFIG_IUCV)		+= iucv/
obj-$(CONFIG_SMC)		+= smc/
obj-$(CONFIG_RFKILL)		+= rfkill/
obj-$(CONFIG_NET_9P)		+= 9p/
obj-$(CONFIG_CAIF)		+= caif/
ifneq ($(CONFIG_DCB),)
obj-y				+= dcb/
endif
obj-$(CONFIG_6LOWPAN)		+= 6lowpan/
obj-$(CONFIG_IEEE802154)	+= ieee802154/
obj-$(CONFIG_MAC802154)		+= mac802154/

ifeq ($(CONFIG_NET),y)
obj-$(CONFIG_SYSCTL)		+= sysctl_net.o
endif
obj-$(CONFIG_WIMAX)		+= wimax/
obj-$(CONFIG_DNS_RESOLVER)	+= dns_resolver/
obj-$(CONFIG_CEPH_LIB)		+= ceph/
obj-$(CONFIG_BATMAN_ADV)	+= batman-adv/
obj-$(CONFIG_NFC)		+= nfc/
obj-$(CONFIG_PSAMPLE)		+= psample/
obj-$(CONFIG_NET_IFE)		+= ife/
obj-$(CONFIG_OPENVSWITCH)	+= openvswitch/
obj-$(CONFIG_VSOCKETS)	+= vmw_vsock/
obj-$(CONFIG_MPLS)		+= mpls/
obj-$(CONFIG_NET_NSH)		+= nsh/
obj-$(CONFIG_HSR)		+= hsr/
ifneq ($(CONFIG_NET_SWITCHDEV),)
obj-y				+= switchdev/
endif
ifneq ($(CONFIG_NET_L3_MASTER_DEV),)
obj-y				+= l3mdev/
endif
obj-$(CONFIG_QRTR)		+= qrtr/
obj-$(CONFIG_NET_NCSI)		+= ncsi/

#ifdef OPLUS_FEATURE_DATA_EVAL
#PengHao@NETWORK.DATA.8124, 2020/05/08, Add for network quality evaluation.
obj-y				+= oplus_kernel2user/
#endif /* OPLUS_FEATURE_DATA_EVAL */

OPLUS_FEATURE_WIFI_LUCKYMONEY=1
ifneq ($(OPLUS_FEATURE_WIFI_LUCKYMONEY),)
#HuangYuan@CONNECTIVITY.WIFI.INTERNET, 2018/06/18, Add for WeChat lucky money recognition
obj-y				+= oplus_nf_hooks/
endif #/* OPLUS_FEATURE_WIFI_LUCKYMONEY */

#ifdef OPLUS_FEATURE_WIFI_SLA
#HuangJunyuan@CONNECTIVITY.WIFI.INTERNET.1197891, 2018/04/10,Add code for appo sla function
obj-y                   	+= oplus_sla/
#endif /* OPLUS_FEATURE_WIFI_SLA */

OPLUS_FEATURE_DHCP=1
ifneq ($(OPLUS_FEATURE_DHCP),)
#LianGenglin@CONNECTIVITY.WIFI.INTERNET, 2020/05/09, Add for Dhcp conflict
obj-y				+= oplus_dhcp/
endif #/* OPLUS_FEATURE_DHCP */

#ifdef OPLUS_FEATURE_NWPOWER
#Asiga@PSW.NW.DATA.2120730, 2019/06/26, add for classify glink wakeup services and count IPA wakeup.
obj-y				+= oplus_nwpower/
#endif /* OPLUS_FEATURE_NWPOWER */

#ifdef OPLUS_FEATURE_APP_MONITOR
#Xiong.Li@TECH.CN.WiFi.Network.2022890,2019/06/14,
#Add for apps network monitors
obj-y				+= oplus_apps_monitor/
#endif /* OPLUS_FEATURE_APP_MONITOR */