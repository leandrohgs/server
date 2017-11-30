# server
#configuration file .conkyrc
use_xft yes
xftfont 123:size=8
xftalpha 0.1
update_interval 0.5
total_run_times 0

own_window yes
own_window_type normal
own_window_transparent yes
own_window_hints undecorated,below,sticky,skip_taskbar,skip_pager
own_window_colour 000000
own_window_argb_visual no
own_window_argb_value 0

double_buffer yes
minimum_size 250 5
maximum_width 500
draw_shades no
draw_outline no
draw_borders no
draw_graph_borders no
default_color white
default_shade_color red
default_outline_color green
alignment top_right
gap_x 0
gap_y 40
no_buffers yes
uppercase no
cpu_avg_samples 2
net_avg_samples 1
override_utf8_locale yes
use_spacer yes


minimum_size 0 0
TEXT
#${voffset 1}${offset 12}${font Ubuntu:pixelsize=12}${color FFA300}HD ${offset 9}$color${fs_free /} / ${fs_size /}${offset 30}${color FFA300}RAM ${offset 9}$color$mem / $memmax${offset 30}${color FFA300}CPU ${offset 9}$color${cpu cpu0}%
# Relogio
${alignc}${color #FF0412}${font Noto Black:size=30}${time %H:%M:%S}${font}${color}
${alignc}${font Arial Black:size=10}${time %A}, ${time %e} de ${time %B} de ${time %G}${font} 
$color
${color CC9900}SISTEMA ${hr 2}$color
Hostmane: $nodename 
Sistema: $sysname $kernel on $machine
Uptime:$color $uptime

${color CC9900}CPU ${hr 2}$color
Total CPU: ${cpu cpu0}%
${color 597DB2}${cpubar}$color
${cpugraph acff82 567fc1}
Core 1: ${freq 1} MHz        ${alignr}Temperatura: $color ${exec sensors|grep 'Core 0'|awk '{print $3}'}
${cpu cpu1}% ${color 597DB2}${cpubar cpu1}$color
Core 2: ${freq 2} MHz        ${alignr}Temperatura: $color ${exec sensors|grep 'Core 1'|awk '{print $3}'}
${cpu cpu2}% ${color 597DB2}${cpubar cpu2}$color
Core 3: ${freq 3} MHz        ${alignr}Temperatura: $color ${exec sensors|grep 'Core 2'|awk '{print $3}'}
${cpu cpu3}% ${color 597DB2}${cpubar cpu3}$color
Core 4: ${freq 4} MHz        ${alignr}Temperatura: $color ${exec sensors|grep 'Core 3'|awk '{print $3}'}
${cpu cpu4}% ${color 597DB2}${cpubar cpu4}$color
#
#NAME            PID CPU%   MEM%
#${color CCFFFF}${top name 1} ${top pid 1} ${top cpu 1} ${top mem 1}
#${top name 2} ${top pid 2} ${top cpu 2} ${top mem 2}
#${top name 3} ${top pid 3} ${top cpu 3} ${top mem 3}
#${top name 4} ${top pid 4} ${top cpu 4} ${top mem 4}$color

${color CC9900}MEMORIA ${hr 2}$color
RAM Usada: ${mem} ${alignr}RAM Livre: ${memfree}/${memmax}
${memgraph FF0000 FF6600}
 RAM: $memperc%  ${color FF6600} ${membar 9}$color
Swap: $swapperc%   ${color FF6600} ${swapbar 6}$color
# uso: $swapperc%   ${color FF6600} ${swap 6}$color
# max: $swapperc%   ${color FF6600} ${swapmax 6}$color
#${cached} #Amount of memory cached

${color CC9900}DISCO ${hr 2}$color
#${hr}
${color F09000}File systems: ${fs_type}    Disc io: ${diskio}
Total /: $color${fs_used /}/${fs_size /} ${color FFFF33}
${fs_free_perc /}% livre ${fs_bar 9 /}$color
${color F09000}Total BACKUP: $color${fs_used /mnt/BACKUP/}/${fs_size /mnt/BACKUP/} ${color FFFF33}
${fs_free_perc /mnt/BACKUP}% livre ${fs_bar 9 /mnt/BACKUP/}$color 
${color F09000}Total 1TB: $color${fs_used /mnt/1TB/}/${fs_size /mnt/1TB/} ${color FFFF33}
${fs_free_perc /mnt/1TB}% livre ${fs_bar 9 /mnt/1TB/}$color 


#sdc5 ${fs_type} (Root): ${fs_free_perc /}% ${color FFFF33} ${fs_bar 6 /}$color
#sdc1 NTFS (Data): ${fs_free_perc /media/}% ${color FFFF33} ${fs_bar 6 /media/}$color
#${color 888888}/home : ${color CCCCCC}${fs_size /home/leandro/}    ${fs_free_perc /home/leandro/} %  ${fs_bar 6 /home/leandro/}
${color CC9900}REDE (${addr enp3s0}) ${hr 2}$color
Down: $color${downspeed enp3s0} k/s  ${alignr}Up: ${upspeed enp3s0} k/s
${downspeedgraph enp3s0 15,170 000000 ff0000}  ${alignr}${upspeedgraph enp3s0 15,170 000000 00ff00}$color
Total Down: ${totaldown enp3s0} ${alignr}Total Up: ${totalup enp3s0}
Inbound: ${tcp_portmon 1 32767 count} ${alignr}Outbound: ${tcp_portmon 32768 61000 count}${alignr}
Total: ${tcp_portmon 1 65535 count}

#${color CC9900}REDE (${addr enp4s0}) ${hr 2}$color
#Down: $color${downspeed enp4s0} k/s |  Up: ${upspeed enp4s0} k/s
#${downspeedgraph enp4s0 15,100 000000 ff0000} | ${upspeedgraph enp4s0 15,100 000000 00ff00}$color
#Total Down: ${totaldown enp4s0} ${alignr}Total Up: ${totalup enp4s0}
#Inbound: ${tcp_portmon 1 32767 count} / Outbound: ${tcp_portmon 32768 61000 count}${alignr}Total: ${tcp_portmon 1 65535 count}
#
#${color CC9900}Wireless Info ${hr 2}$color
#SSID: ${wireless_essid wlp3s0}        ${alignr}Canal: ${wireless_channel wlp3s0}
#Frequencia ${wireless_freq wlp3s0}    ${alignr}Qualidade: ${wireless_link_qual_perc wlp3s0}
#Modo: ${wireless_mode wlp3s0}
#
${color CC9900}TOP PROCESSES ${hr 2}$color
Quantidade de processos:${color 339900} ${processes}
${color FF0000}${top_mem name 1}${alignr}${top mem 1} %
${top_mem name 2}${alignr}${top mem 2} %
$font${top_mem name 3}${alignr}${top mem 3} %

#${color CC9900}LOGADOS ${hr 2}$color
#${exec command who}
#
#${color CC9900}TESTES ${hr 2}$color
#${cpugauge} 
#${memgauge}
#${execpi 1 /home/leandro/.conky_ping.sh 192.168.1.251}
#Ping UOL: ${exec ping -c 1 www.uol.com.br | grep time= | awk '{print $8}' | cut -d '=' -f2}ms
#Ping TYR: ${exec ping -c 1 192.168.1.251 | grep time= | awk '{print $7}' | cut -d '=' -f2}ms
#
#${color CC9900}GMAIL ${hr 2}$color
#${execi 300 python ~/.gmail.py}
