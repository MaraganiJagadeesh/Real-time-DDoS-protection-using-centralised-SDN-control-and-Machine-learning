# Real-time-DDoS-protection-using-centralised-SDN-control-and-Machine-learning
DDoS Detection Using Ryu SDN Controller and Machine Learning

This project demonstrates a DDoS detection system built with:
- A custom Mininet topology
- A Ryu controller application
- A Decision Tree-based ML classifier using flow statistics

How to Run the DDoS Detection System

1. Install the Required Dependencies

Install these in your VirtualBox Linux VM:
- Python 3.6 or higher
- Ryu SDN Framework: pip install ryu
- Mininet: sudo apt install mininet
- ML Libraries: pip install scikit-learn pandas matplotlib
- xterm (for GUI host terminals): sudo apt install xterm

2. Start the Ryu Controller

cd ryu_app
ryu-manager ddos_detector.py

3. Launch the Custom Mininet Topology

cd topology
sudo python3 custom_topology.py

4. Open Host Terminals

From Mininet CLI:
xterm h1 h2 h3 h4 &

5. Simulate Traffic

Use ping or hping3 to simulate traffic. For example:
h1 hping3 -S -p 80 --flood h6

6. Run the Classifier on Collected Data

After some traffic has been generated:
cd classifier
python3 traffic_classifier.py

7. Check Output

- If DDoS is detected, alerts or classification labels will be printed.
- Confusion matrix or logs may show classification performance.
