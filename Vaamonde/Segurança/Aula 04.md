Objetivo a aula de hoje: 12/03/2024 (CONTINUAÇÃO)

CUIDADO COM AS PLACAS DE REDE ON-BOARD E OFF-BOOARD NAS MÁQUINAS VIRTUAL, VERIIFCAR SE ESTÁ PEGANDO ENDEREÇO IPV4 E SE ESTÁ PINGANDO A INTERNET (VAMOS RETORMAR OS PROCEDIMENTOS DE IP E CONFIGURAÇÕES DE REDE PARA O MELHOR ENTENDIMENTO).

Conceitos Básicos de Segurança Windows, GNU/Linux, Redes de Computadores e Usuários Finais:

	#01_ Material de Apoio das Aulas:



NIC.br (Núcleo de Informação e Coordenação do Ponto BR.br)
https://nic.br/

CERT.br (Centro de Estudos, Resposta e Tratamento de Incidentes de Segurança no Brasil)
https://www.cert.br/

Fascículos: https://cartilha.cert.br/fasciculos/#redes
			https://cartilha.cert.br/fasciculos/#computadores

	#02_ Entendendo as diferenças das Placas de Rede do VirtualBOX
	#A_ NAT.....: https://www.virtualbox.org/manual/ch06.html#network_nat
	#B_ BRIDGE..: https://www.virtualbox.org/manual/ch06.html#network_bridged
	#C_ INTERNA.: https://www.virtualbox.org/manual/ch06.html#network_internal


#03_ Endereçamento IPv4 Linux e Windows
	Windows: Conexões de Rede
		Conexão Local
			Propriedades
	
	Linux..: Configurações de Rede
		Cabeada
			Engrenagem
	
	Nomes de computadores iguais ou Endereços
	IP.
	
	Comandos Básicos de Redes Windows e Linux
	
	Windows					Linux
	ipconfig				ifconfig
	ipconfig /all			route -n
							resolvectl
	ipconfig /release		sudo ifconfig enp0s3 down
	ipconfig /renew			sudo ifconfig enp0s3 up
	ipconfig /displaydns	resolvectl statistics
	ipconfig /flushdns		resolvectl flush-caches
							resolvectl reset-statistics
	route print				route -n
	ping 8.8.8.8			ping 8.8.8.8
	tracert 8.8.8.8			sudo apt update
							sudo apt install traceroute
							traceroute 8.8.8.8
	nslookup 8.8.8.8		nslookup 8.8.8.8
	hostname				hostname

	#04_ Firewall Linux e Windows

#Windows
Iniciar, Painel de Controle, Firewall do Windows
	Avançado, ICMP, Configurações
		Permitir solicitação de ECHO de Entrada

#Linux
Negar ICMP...: sudo sysctl net.ipv4.icmp_echo_ignore_all=1
Permitir ICMP: sudo sysctl net.ipv4.icmp_echo_ignore_all=0

	#05_ Conceito Básico de Rede Workgroup

Workgroup:
Domínio..:

	#06_ Testando as conexões
