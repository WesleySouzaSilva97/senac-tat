Objetivo a aula de hoje: 07/03/2024

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
			
	Comandos Básicos de Redes Windows e Linux
	
	Windows					Linux
	ipconfig				ifconfig
	ipconfig /all				route -n
						resolvectl
	ipconfig /release			sudo ifconfig enp0s3 down
	ipconfig /renew				sudo ifconfig enp0s3 up
	ipconfig /displaydns			resolvectl statistics
	ipconfig /flushdns			resolvectl flush-caches
						resolvectl reset-statistics
	route print				route -n
	ping 8.8.8.8				ping 8.8.8.8
	tracert 8.8.8.8				sudo apt update
						sudo apt install traceroute
						traceroute 8.8.8.8
	nslookup 8.8.8.8			nslookup 8.8.8.8

#04_ Firewall Linux e Windows

#Windows
