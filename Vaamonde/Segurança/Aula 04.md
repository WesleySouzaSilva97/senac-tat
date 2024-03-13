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

---

#03_ Endereçamento de redes

```
Endereçamento IPv4 Linux e Windows
	Windows: Conexões de Rede
		Conexão Local
			Propriedades

Linux..: Configurações de Rede
		Cabeada
			Engrenagem
```

---

|Comandos básicos de redes - Windows e Linux|
:---

Verificação de endereçamento do IP 

	Windows					Linux
 
	ipconfig				ifconfig
	ipconfig /all				route -n
                                		resolvectl


Visualização de tabela de roteamento (para descobrir o Gateway padrão)

 	Windows					Linux

	route print 				route -n

Configuração do endereçamento do IP (renovação da concessão)

	Windows					Linux
 
	ipconfig /release			sudo ifconfig enp0s3 down
	ipconfig /renew				sudo ifconfig enp0s3 up

Visualização das estatísticas de cache de navegação

	Windows					Linux

	ipconfig /displaydns			resolvectl statistics

 Limpar as estatísticas de cache de navegação
 
	Windows					Linux

	ipconfig /flushdns			resolvectl flush-caches
						resolvectl reset-statistics
      
---

Ping - Avaliar a conexão da rede de equipamentos internos (computadores, impressoras, máquinas etc) e a conexão com servidores de internet e endereços de sites específicos, determinando o tempo de latência da resposta entre as máquinas

	Windows					Linux
 
	ping 8.8.8.8				ping 8.8.8.8
  	ping 8.8.8.8 -t (intermitente)

Se o tempo de resposta estiver acima de 100/150ms (milissegundos) pode ter ocorrido algum problema com a rede de internet

Uma boa conexão de rede é abaixo de 10ms (milissegundos)

---

Avaliar a conexão da rede - Verificação da rota completa do endereçamento do IP

 	Windows					Linux

						sudo apt update
						sudo apt install traceroute
	tracert 8.8.8.8				traceroute 8.8.8.8


Verificar se as configurações de rede dos servidores DNS (Domain Name System / Sistema de Nomes de Domínio) está configurada de forma correta

  	Windows					Linux

 	nslookup 8.8.8.8			nslookup 8.8.8.8

Verificar o nome do computador

  	Windows					Linux

	hostname			hostname
 
 #04_ Firewall Linux e Windows

	PINGAR WINDOWS ----> 	LINUX MINT
	LINUX MINT ----> 	PINGAR WINDOWS 
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
