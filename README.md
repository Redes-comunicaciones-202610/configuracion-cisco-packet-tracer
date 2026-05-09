Configuración del proyecto en cisco packet tracer.
Versión a partir de la entrega 26-marzo.

**TODO**:
- Configurar las sucursales de cada departamento, con sus respectivas VLANs, y configurar el router para que se comuniquen entre sí.
- Desde develop se deben sacar ramas para cada departamento y realizar las configuraciones correspondientes.
- Guardar el proyecto en la carpeta del repositorio y subirlo a GitHub.


**Configuración de la red en la sucursal "La Libertad":**
- Configurar cada switch para que tenga las VLANs correspondientes a cada departamento (VLAN 110 para Servidores, VLAN 120 para Administración, VLAN 130 para Marketing, VLAN 140 para RRHH).

    - (SW1-CAPA3-LALIBERTAD)
            

            enable
            configure terminal
            hostname CORE_LALIBERTAD

            
            vlan 110
            name SERV
            exit

            
            vlan 120
            name ADMIN
            exit

            
            vlan 130
            name MARKETING
            exit

            
            vlan 140
            name RRHH
            exit

            
            interface GigabitEthernet1/0/1
            switchport mode trunk
            switchport trunk vlan allowed all
            exit

            
            interface GigabitEthernet1/0/2
            switchport mode trunk
            switchport trunk allowed vlan all
            exit

            
            interface GigabitEthernet1/0/4
            switchport mode trunk
            switchport trunk allowed vlan all
            exit

            
            interface GigabitEthernet1/0/8
            switchport mode trunk
            switchport trunk allowed vlan all
            exit

            
            interface vlan 110
            ip address 10.193.47.129 255.255.255.248
            no shutdown
            exit

            
            interface vlan 120
            ip address 10.193.44.1 255.255.254.0
            no shutdown
            exit

            
            interface vlan 130
            ip address 10.193.46.1 255.255.255.0
            no shutdown
            exit

           
            interface vlan 140
            ip address 10.193.47.1 255.255.255.128
            no shutdown
            exit

            
            ip routing
            


    - (SW1-LALIBERTAD)
            
        
            enable
            configure terminal
            hostname SW1_LALIBERTAD

            
            vlan 110
            name SERV
            exit

            
            vlan 120
            name ADMIN
            exit

            
            vlan 130
            name MARKETING
            exit

            
            vlan 140
            name RRHH
            exit

            
            interface range fa0/1-3
            switchport mode access
            switchport access vlan 120
            exit

            
            interface Gig0/1
            switchport mode trunk
            switchport trunk vlan allowed all
            exit
            


    - (SW2-LALIBERTAD)
            

            enable
            configure terminal
            hostname SW2_LALIBERTAD
            
            vlan 110
            name SERV
            exit

            
            vlan 120
            name ADMIN
            exit

            
            vlan 130
            name MARKETING
            exit

            
            vlan 140
            name RRHH
            exit

            
            interface range fa0/1-2
            switchport mode access
            switchport access vlan 130
            exit

            
            interface fa0/4
            switchport mode access
            switchport access vlan 140
            exit

            
            interface Gig0/1
            switchport mode trunk
            switchport trunk vlan allowed all 
            exit
            

    - (SW3-LALIBERTAD)
            

            enable
            configure terminal
            hostname SW3_LALIBERTAD

            
            vlan 110
            name SERV
            exit

           
            vlan 120
            name ADMIN
            exit

            
            vlan 130
            name MARKETING
            exit

            
            vlan 140
            name RRHH
            exit

            
            interface range fa0/1-5
            switchport mode access
            switchport access vlan all
            exit

            
            interface Gig0/1
            switchport mode trunk
            switchport trunk vlan allowed all
            exit
            

    

        

    
    

        
        

