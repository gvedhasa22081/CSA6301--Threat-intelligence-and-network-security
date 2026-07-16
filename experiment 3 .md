<img width="868" height="387" alt="image" src="https://github.com/user-attachments/assets/bbc91e88-9052-40ee-9a1a-5db7cd6e7112" />
import socket

# Function to scan ports
def scan_ports(target, start_port, end_port):
    print(f"\nScanning {target} from port {start_port} to {end_port}...\n")

    for port in range(start_port, end_port + 1):
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.settimeout(0.5)

        result = s.connect_ex((target, port))

        if result == 0:
            print(f"Port {port}: OPEN")

        s.close()

# Main Program
target = input("Enter target IP address or hostname: ")
start_port = int(input("Enter starting port: "))
end_port = int(input("Enter ending port: "))

scan_ports(target, start_port, end_port)
