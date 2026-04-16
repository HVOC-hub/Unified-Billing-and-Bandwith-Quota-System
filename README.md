# IT-Project-2
Unified Bandwith and Billing Quota system

SYSTEM DEVELOPMENT LIFE CYCLE
1) Environment setup
   install virtual box
   import microtik CHR and create a new VM
   configure network adapters(for the laptop to talk to the router and for the router to gain internet access)
   install winbox and connect to the CHR mac address or the host-only IP
2) Database design (to track users and their data consumption)
   install zampp/mysql
   create the database (isp_billing)
   define the tables (users, vouchers, usage_logs)
3) Backend logic and router API (the brain)\
   enable the microtik API
   write the python scripts(enforcers) connection, checks and throttling
4) Accounting and polling
   connect the routers to the database to document the usage at the database
   create a polling script(a script that runs every minute)\
   fetching data
   update DB
5) Admin dashboard (the interface)
   build the framework
   features(voucher generation, live monitor, kill switch)
6) Testing and validation
   functional testing - does the database update
   SLA testing - does the throttling work when the voucher expires
   Security testing - does changing the ip address do anything   


# Progress log : phase 1
(INFRASTRUCTURE)
Established the core networking environment.
**Router Engine** Deployed MikroTik CHR(Cloud Hosted Router) v7.20.8 on virtualbox.
**Networking** Configured a host only adapter for a dedicated management network.
**Static Addressing** assigned static ip 192.168.56.10 to the CHR for reliable API communication
                     assigned static ip 192.168.56.1 to the virtual box host-only ethernet adapter
**Connectivity** Verified communication via winbox and ICMP (ping)
