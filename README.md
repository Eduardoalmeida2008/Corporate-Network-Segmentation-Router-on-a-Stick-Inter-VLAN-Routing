# Inter-Vlan-routing-com-DHCP
Este laboratório simula um ambiente corporativo básico, com segmentação de rede utilizando VLANs, comunicação entre redes via roteamento inter-VLAN (Router-on-a-Stick) e distribuição automática de IPs via DHCP.  O objetivo é demonstrar conhecimento prático em infraestrutura de redes, seguindo boas práticas utilizadas em ambientes reais.

```
📌 Topologia do Ambiente
2 Switches Layer 2
1 Roteador (Router-on-a-Stick)
3 VLANs- 3PCs cada
Trunk entre switches
📷 Ver imagem da topologia em /topology/topology.png
```

```
Trunk entre switch e roteador
DHCP centralizado no roteador
```

````
🧱 VLANs Configuradas
VLAN	Nome	Rede
10	Administrativo	192.168.10.0/24
20	Financeiro	192.168.20.0/24
30	TI	192.168.30.0/24
Cada VLAN representa um setor da empresa, com isolamento de broadcast.
````

````
🔀 Trunking (802.1Q)
Porta trunk entre Switch 1 ↔ Switch 2
Porta trunk entre Switch 1 ↔ Roteador
VLANs permitidas: 10, 20 e 30
Encapsulamento: 802.1Q
📷 Evidência: show interfaces trunk
````

````
🌐 Roteamento Inter-VLAN
O roteamento entre VLANs foi implementado usando Router-on-a-Stick, com subinterfaces no roteador:
G0/0.10 → VLAN 10
G0/0.20 → VLAN 20
G0/0.30 → VLAN 30
Cada subinterface atua como gateway padrão da sua VLAN.
📷 Evidência: show ip interface brief
````

````
📡 DHCP por VLAN
O roteador atua como servidor DHCP, com um pool para cada VLAN:
Entrega automática de IP
Gateway padrão configurado corretamente
Isolamento por rede
Todos os PCs receberam IP automaticamente conforme sua VLAN.
📷 Evidência: show ip dhcp binding
````

```´
🧪 Testes Realizados
✔ PCs recebem IP via DHCP
✔ Comunicação entre dispositivos da mesma VLAN
✔ Comunicação entre VLANs diferentes
✔ Teste de conectividade usando ping
📷 Evidência: prints dos testes de ping
````

```
🧠 Conceitos Aplicados
VLANs e segmentação de rede
Trunk 802.1Q
Roteamento inter-VLAN
DHCP em ambientes segmentados
Boas práticas de organização de rede
````

````
📚 Ferramentas Utilizadas
Cisco Packet Tracer
Switches Cisco Layer 2
Roteador Cisco ISR
CLI Cisco IOS
````

````
📌 Autor
Eduardo
Estudante de TI focado em Infraestrutura, Redes e Freelancing Técnico
```
