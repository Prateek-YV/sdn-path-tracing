# SDN Path Tracing Tool using Mininet and Ryu

## 🔴 Problem Statement

To implement a Software Defined Networking (SDN) based Path Tracing Tool that identifies and displays the path taken by packets using Mininet and the Ryu controller.

---

## 🎯 Objective

* Track packet flow in a network
* Display the path taken by packets
* Implement OpenFlow match-action rules
* Analyze normal and failure conditions

---

## ⚙️ Tools Used

* Mininet
* Ryu Controller
* OpenFlow
* Ubuntu VM

---

## 🧠 Working

The controller listens for packet_in events, learns MAC addresses, installs flow rules, and prints the switches through which packets pass, allowing path tracing.

---

## 🛠️ Steps to Run

### 1. Start Controller

```
ryu-manager path_tracer.py
```

### 2. Start Mininet

```
sudo mn --topo single,3 --controller=remote
```

### 3. Test

```
h1 ping -c 5 h3
```

### 4. Flow Table

```
sh ovs-ofctl dump-flows s1
```

### 5. Failure Case

```
link s1 h3 down
h1 ping -c 5 h3
```

---

## 📊 Output

### Path Trace

Packets are traced through switches:

```
Packet → switch 1 → switch 2 → switch 3
```

---

## 🧪 Test Cases

### ✅ Normal Case

* Ping successful
* Path displayed

### ❌ Failure Case

* Link is disconnected
* Ping fails

---

## 📸 Screenshots

* Topology
* Ping success
* Ping failure
* Path trace
* Flow table

---

## ✅ Conclusion

The project demonstrates SDN-based path tracing using controller logic and OpenFlow rules.

---

## 📚 References

* Mininet Documentation
* Ryu Documentation
