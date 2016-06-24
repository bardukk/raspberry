#!/bin/bash

ensenya_menu(){
    var=$(lsb_release -a )
    if [[ $var == *jessie* ]]
    then
        var=1;
    else
    	if [[ $var == *wheesy* ]]
    	then
    		var=0;
    	fi
    fi
	
	clear
    NORMAL=`echo "\033[m"`
    MENU=`echo "\033[36m"` #Blue
    NUMBER=`echo "\033[33m"` #yellow
    FGRED=`echo "\e[1;35m"`
    RED_TEXT=`echo "\033[31m"`
    ENTER_LINE=`echo "\033[33m"`
    SALT=`echo ""`
    echo -e "${SALT}"
    echo -e "${SALT}"
    echo -e "${RED_TEXT}       MENU CONFIGURACIO RASPBERRY PI ${NORMAL}"
    echo -e "${SALT}"
    echo -e "${SALT}"
    echo -e "${NUMBER}     1)${MENU} ACTUALITZAR RASPBERRY PI ${NORMAL}"
    echo -e "${NUMBER}     2)${MENU} ACTUALITZAR KERNEL${NORMAL}"
    echo -e "${NUMBER}     3)${MENU} INSTAL·LAR DRIVERS TP-LINK ${NORMAL}"
    echo -e "${NUMBER}     4)${MENU} INSTAL·LAR MONO ${NORMAL}"
    echo -e "${NUMBER}     5)${MENU} INSTAL·LAR WIRINGPI ${NORMAL}"
    echo -e "${NUMBER}     6)${MENU} Sortir ${NORMAL}"
    echo -e "${SALT}"
    echo -e "${ENTER_LINE}    Entra un numero i prem enter ${NORMAL}"
    read opt
}
function option_picked() {
    COLOR=`echo "\033[01;31m"` # bold red
    RESET=`echo "\033[00;00m"` # normal white
    MESSAGE=${@:-"${RESET}Error: Cap Missatge Passat"}
    SALT=`echo ""`
    echo -e "${SALT}"
    echo -e "${SALT}"
    echo -e "${COLOR}${MESSAGE}${RESET}"
    echo -e "${SALT}"
}
function Actualitzar_Raspberry(){
    COLOR=`echo "\033[01;31m"` # bold red
    RESET=`echo "\033[00;00m"` # normal whit
    SALT=`echo ""`
    sudo apt-get -y update
    sudo apt-get -y upgrade
	sudo apt-get install rpi-update
    sudo rpi-update
    echo -e "${SALT}${COLOR} Raspberry Actualitzada ${NORMAL}${SALT}${SALT}"
    sudo reboot
}
function Instalar_NodeRed(){
    COLOR=`echo "\033[01;31m"` # bold red
    RESET=`echo "\033[00;00m"` # normal whit
    SALT=`echo ""`
    if [[ $var == 1 ]]
    then
		echo"HOLA"
	fi
	if [[ $var == 0 ]]
    then
		echo"ADEU"
	fi
    echo -e "${SALT}${COLOR} Raspberry Actualitzada ${NORMAL}${SALT}${SALT}"
    sudo reboot
}
function Install_Mono(){
    COLOR=`echo "\033[01;31m"` # bold red
    RESET=`echo "\033[00;00m"` # normal whit
    SALT=`echo ""`
    sudo apt-get -y update
    sudo apt-get -y install mono-complete
    echo -e "${SALT}${COLOR} Mono Instal·lat ${NORMAL}${SALT}${SALT}"
}
function Install_WiringPi(){
    COLOR=`echo "\033[01;31m"` # bold red
    RESET=`echo "\033[00;00m"` # normal whit
    SALT=`echo ""`
    cd ~
    sudo apt.get install git-core
    git clone git://git.drogon.net/wiringPi
    cd wiringPi
    ./build
    echo -e "${SALT}${COLOR} WiringPi Instal·lat ${NORMAL}${SALT}${SALT}"
}

ensenya_menu;
while [ opt != '' ]
    do
        case $opt in

        1) clear;
           option_picked "Acutalitzant Raspberry Pi";
           Actualitzar_Raspberry;
           sleep 10
           ;;

        2) clear;
           option_picked "Actualitzar Kernel";
           Actualitzar_Kernel;
           sleep 10
           ;;

        3) clear;
           option_picked "Instal·lar drivers TP-Link";
           Drivers_TP-link;
           sleep 10
           ;;
        
        4) clear;
		   option_picked "Instal·lar mono";
           Install_Mono;
           sleep 3
           ensenya_menu;
           ;;

        5) clear;
           option_picked "Instal·lar WiringPi";
           Install_WiringPi;
           sleep 3
           ensenya_menu;
           ;;

        6) clear;
           exit;
           ;;

        x)exit;
           ;;

        \n)exit;
           ;;

        *) clear;
           option_picked "Tria una opcio del menu";
           ensenya_menu;
           ;;
    esac
done
