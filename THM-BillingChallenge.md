##BillingChallenge
*Some mistakes can be costly.*

#### **Methodology** 

Started the machine and scanned for vulnerabilities and open ports using Nmap finding that port 22,80 and 3306 were open

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfaXnzTWszDnp-iCFbAavTUwBHFwydq65wzM_pNclMtAQxXBDfUu6e8Th8zhWqWL6eTtt2KEEPYRMyslRUK4fvtxVTcyOMvPd4-aYbGJvq-7FikoON6Yz8vrXTFnJsh-gPjj_gf?key=Alqzz-cY4k7hF6ju5NjQIZde)

Accessed the machine via port 80 http and was met with login page

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdI9nC3rOOUSZgv9Fx3FKfJ0Tbn0OGnV-kVJhaTqribFdbiaVSDyipEty0bhfIcDmercrS6wWHEvzPVZeuGj38zV0k2J-KODI7PpgBe9ZyVHK-Z_jcvYwurxz1TIupTVP_ZWuCdmQ?key=Alqzz-cY4k7hF6ju5NjQIZde)

Researched the internet on existing vulnerabilities for the mysql MariaDB version being used on the machine

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfl9sDkp3uhMSuXhSP9OJrBaXS1nXnozSzLtgCR1eACHWhiZqtkq941CYMZMaHuZNTPe4QKgX8xOt1gkkEGCOVErtPZNTpr0sGkMH8m2kFbBCtaj2qK0ix1Jssp5C39uPGqfjqEag?key=Alqzz-cY4k7hF6ju5NjQIZde)

Googled on the exploitation of the web application using its name (magnusBilling)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcCYKDjHIVQjJaPiNGDAp73UdLGGlN5CIXuytYfin0-Az3UcyL-48Zw6t_yPGhzd5Od_pU4LWQFP9e3--qTbibfK2K5lEtlZbOvciiL236kdYQ7_Xg1CvUlrtFXQJkUE3JbsftxeA?key=Alqzz-cY4k7hF6ju5NjQIZde)

Found a metasploit module that we can use to exploit the application using rce

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcDCFb5k22AHAgbzizs24fRUdtzq6yMv_3yrkOjeYdF-CQpj0svTO09IK6Dz97y9VuWggbcszmBPqLgWCHrmUcVk8RJCmg69jSZ4SNMPdlMAS09jcCWLHanSwydCG1vUQyW_LTE?key=Alqzz-cY4k7hF6ju5NjQIZde)

Set the required options for the module 

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfWuzf1XEkvBiTFnyuaR2_43L9R_ypjtPNFp-YY7LIs7dKyYPMk4kSgYiJIuQyRjZgwC03rZzvGlUNI2qntPs4GyKIitnv3SPFtq5RbWmosgcmbeFBkq1_Sv6uCoCuifFQfJ8en?key=Alqzz-cY4k7hF6ju5NjQIZde)

Executed the module and obtained a meterpreter shell

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdcEboko9OEHZdc36ROOT1z2VdXF-oQ_2dPLhloPzKPa_6ov_Ca7OQGX1BUxFeYPcUhc20B0VP39vtdPiPhTfIYxm_BKcHwtT2e9giqbbaoagwQHAqTFuSJ_96yuFlrLSa6QjnjaQ?key=Alqzz-cY4k7hF6ju5NjQIZde)


Obtained user.txt file from the machine

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcB1rSyuG-xBb7MSvoimkOW5BxDZ57tlmGjjuQYodKkdi0F2B2V7XLUU78WdmHaf9dDjXaEVz12EDbPv5KZMXLclUna9QpzKMbYZjfORXSV9-b8oRyrFz1hwx_aG7bHeV8GHUYT?key=Alqzz-cY4k7hF6ju5NjQIZde)

Tried accessing root and got the following response with a file that can be run without need for root permissions

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe5cdOvnrSqYGo6iV72HnYszz0C8cYFDdaxyEAYWIIs6pWhw0WFO4a141T1py4KC2f0Oyx7F0tKFWU3c1qEabvb-BVjJzLOoi8PSXdewPGhsyid3ylV-jrlP1KuusDQke1dkM55?key=Alqzz-cY4k7hF6ju5NjQIZde)

The file is fail2ban which is an IP address blocking tool

Researched on the internet on how to privilege escalate using the file fail2ban

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcur5gjjaZfGz965CGtvFFmgTsmX_4TLcqR6db2ecGcjc6Uo09Lae68rOQkDTNB_NFu5HFLyowsOYUwShu3h-eYBjvpYivcPeqfShDXQnX74soVCv5CqfpUEBPY4Op525CiCxvh?key=Alqzz-cY4k7hF6ju5NjQIZde)

Accessed the fail2ban directory

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe-fOCEMmMbpx4ly0itQ6p8tH5jsHsW0eoB9tCHbWewgeIQuQptQ-qfXQIfrDpSYtLbir55-akOCuWTfLlHaBbqI6mWt2V7VeGVvbckvXUef1IQI0BmN14EhnlyPINKOpUUuq1Orw?key=Alqzz-cY4k7hF6ju5NjQIZde)

Enumerated the file 

Run the command sudo /usr/bin/fail2ban-client status to obtain the names and number of services in the jail list and found sshd to be one of them

We are going to leverage this service to escalate privileges 

Obtained payloads to use to escalate privileges 

Restarted the fail2ban-client tool and then loaded the payloads

The payload exploited the sshd service and accessed the file root.txt changing its mod to 777 

Used the service sshd to ban the ip 127.0.0.1

Accessed the file root.txt
