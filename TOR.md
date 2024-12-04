# x) Read and summarize (briefly, e.g. with some bullets)
### Dingledine, Mathewson and Syverson 2004: Tor: The second-generation onion router. In USENIX security symposium (jufo level 2). Chapter: 3 Design goals and assumptions
Tor, short for The Onion Router, is a powerful tool in online privacy and anonymity it offers a shield of protection for users who value their privacy.

Tor's mission is to keep your online activities hidden from prying eyes. It's like having an invisibility cloak for your internet presence. The network achieves this by routing your internet traffic through a series of volunteer-operated servers, making it incredibly difficult for anyone to trace your online footsteps back to you.

Tor's design is elegant in its simplicity. It focuses on proven techniques to protect anonymity, making it accessible to both tech-savvy users and those less familiar with complex security measures. This user-friendly approach is crucial, as it allows Tor to be compatible with many familiar applications, ensuring that privacy doesn't come at the cost of convenience.

But one should not consider Tor as a magic solution against all problems related to online privacy; it has been designed to attain certain goals while considering some limitations. For example, although Tor is very good at preventing the linking of communication partners and multiple communications to a single user, it does not claim to be impenetrable against all types of attacks.

The network works within a realistic threat model in that it considers adversaries who can observe parts of network traffic and change it, or even compromise parts of the nodes in the network. Despite these kinds of possibilities, Tor is tough and concentrates on preventing traffic analysis attacks rather than traffic confirmation attacks.

Tor's effectiveness lies in its ability to create a maze-like path for your internet traffic. This makes it extremely challenging for anyone to build user behavior profiles or link users to their communication partners. It's like sending a letter through a series of intermediaries, each only knowing the previous and next stop, but never the full journey.

While Tor provides robust protection, it's not without its vulnerabilities. Potential attacks could include attempts to decrease network reliability or subvert directory servers. However, the Tor Project continuously works to address and mitigate these risks, making it a dynamic and evolving system.



### Karunanayake, Ahmed, Malaney, Islam and Jha 2021: De-anonymisation attacks on tor: A survey. In IEEE Communications Surveys & Tutorials (jufo level 2). Chapters: Abstract,I Introduction, II Background (to the end of "B. Circuit Establishent for Tor HS"), Fig. 6. Taxonomy for Tor attacks (Just the figure on page 2330.)

Tor is a popular anonymity network that protects users' online privacy. It works by routing internet traffic through multiple volunteer-operated servers.

#### Main components of Tor include:
Onion Proxy (OP): Software on user's device

Directory Servers (DS): Maintain network information

Entry Node/Guard: First relay in the circuit

Exit Node: Final relay before reaching destination

Hidden Services (HS): Anonymous websites ending in .onion

#### Tor circuit establishment:
OP contacts DS for list of relays

OP selects three relays (entry, middle, exit)

Circuit is created using encryption key exchanges

### Hidden Service connections involve:
Introduction Points: Relays chosen by HS to advertise its service

Rendezvous Points: Relay chosen by client to connect with HS

#### Things to note:
Bridges are unlisted relays that help bypass censorship of Tor.

Tor uses fixed-length cells (512 bytes) for communication to make traffic analysis harder.

De-anonymization attacks on Tor aim to uncover users' identities or reveal hidden services.

#### illustrations:
The paper includes several diagrams that illustrate key components and processes of the Tor network:
Standard Tor circuit: Figure 1 shows the basic components of a Tor network for a standard circuit, including the client, entry node, middle node, exit node, and destination server.

Hidden Services circuit: Figure 2 depicts the components involved in a Hidden Services (HS) connection, such as the client, introduction points, rendezvous point, and the hidden service itself.

Key exchange process: Figure 3 illustrates the Diffie-Hellman handshake used for encryption key exchange during circuit establishment.

Hidden Service connection establishment: Figure 4 shows the steps involved in establishing a connection between a user and a Hidden Service, including interactions with Directory Servers and Introduction Points.

Tor cell structure: Figure 5 presents the structure of Tor's fixed-length cells (512 bytes), showing the differences between control cells and relay cells.

These diagrams help visualize the complex processes and components involved in Tor's anonymity network, making it easier to understand how the system works and where potential vulnerabilities might exist.



### Halonen, Ollikainen, Rajala 2023: PhishSticks - The Ethical Hackers tool for BadUSB (Video, about 3 minutes)
The video describes a fictional scenario demonstrating a USB-based hacking technique. A device called "Fish Sticks" is used to simulate a BadUSB attack. The attacker, an ethical hacker named Steve, leaves the Fish Sticks device on a CEO's desk.

#### When plugged in, Fish Sticks:
Injects keystrokes to open Windows Run

Uses PowerShell to fetch a payload

Installs a keylogger on the target computer

The keylogger records all keystrokes, potentially capturing sensitive information like passwords. The logged data is temporarily stored, then sent to the attacker via HTTP post. The attack is quick and nearly invisible to the user.

The video aims to highlight the importance of information security and the risks of USB-based attacks.




# a) Install TOR browser and access TOR network (.onion addresses). (Explain in detail how you installed it, and how you got access to TOR).
Opened my virtual machine

Opened the web browser within the VM

went to the official Tor Project website (torproject.org) and downloaded browser.
![downloaded tor browser for linux vm](https://github.com/user-attachments/assets/4ab8df9b-46d5-449e-963d-3687c63a1390)

When opening the file i have to extract the content before running it.

I got an attention message of untrusted application launcher. I marked it as executable. 
![untrusted application launcher](https://github.com/user-attachments/assets/ec602e39-8e59-4d1c-a79c-92dafb9c4c38)

getting error while trying to connect. (browser not connecting)

![browser not connecting to tor try a bridge  1](https://github.com/user-attachments/assets/6c8b0101-3c45-4aea-941a-f9e37d691488)

i tried to connect by configuring browser still did not work.
![configured browser to try an connect to the internet](https://github.com/user-attachments/assets/56e9dab1-4d89-4cab-8ca3-47f1a4b05dde)

### install tor browser from vm terminal. (approach given by Tero)
sudo apt-get update 

sudo apt-get -y install tor torbrowser-launcher 

torbrowser-launcher

getting multiple errors.

![errors when installing tor in terminal](https://github.com/user-attachments/assets/76221508-2f4d-4d94-94aa-5b44680ec109)




### install tor browser from vm terminal. (my own approach)
i decided to follow the following procedure to install tor.

sudo apt update

sudo apt install -y tor torbrowser-launcher

torbrowser-launcher

Getting some errors when doing sudo apt update some debian files not available (picture 2)
![sudo apt update error 2](https://github.com/user-attachments/assets/cf0ff010-e9c2-4adc-bdf3-2fb653784ca0)

Error torbrowser-launcher has no installation candidate
![has no installation candidate error 3](https://github.com/user-attachments/assets/9ae23ede-982d-448e-a25d-29b079b29478)





# b) Browse TOR network.
Find, take screenshots and comment

   -search engine for onion sites

   -human rights or civil rights organization

   -marketplace

   -fraud

   -forum

   -a well known organization (with regular postal addresses, offices or similar presence outside darknet)

Use .onion addresses inside TOR network, not regular (clearnet) websites through exit nodes.




# c) Onion. In your own words, how does anonymity work in TOR? (e.g. how does it use: public keys, encryption, what algorithms? This subtask does not require tests with a computer.)
Tor (The Onion Router) achieves anonymity through a technique called onion routing, which uses multiple layers of encryption and a network of relay nodes. This multi-layered approach ensures that no single node in the network knows both the origin and the destination of the data, providing anonymity for the user.

Tor is like a super-secret postal system where your message gets wrapped in multiple envelopes. Each envelope has a special lock that only one specific postal worker can open. When you send a message, it goes through three different postal workers (nodes), and each one only knows where to send the next envelope, but not who originally sent the message or where it's ultimately going. By the time the last postal worker opens the final envelope, they can't trace back to you. It's like passing a secret note through friends, where each friend only knows the person who gave them the note and the person they're giving it to next. This way, nobody can connect the original sender to the final destination.

#### REFERENCE:
https://strathprints.strath.ac.uk/88853/7/Choorod-etal-IEEE-Access-2024-Classifying-Tor-traffic-encrypted-payload-using-machine-learning.pdf 
https://spec.torproject.org/rend-spec/encrypting-user-data.html 
https://en.wikipedia.org/wiki/Tor_(Anonymous_network) 




# d) What kind of threat models could TOR fit? (This subtask does not require tests with a computer.)
Tor is great for avoiding snooping from your internet provider, getting around websites that are blocked in your country, and keeping your identity secret when browsing. 
It's useful for journalists, activists, or anyone who wants to keep their online activities private. 
However, it's not perfect - if someone is watching both the start and end of your Tor connection, they might figure out what you're doing. Also, Tor can be slow, and some websites might not work well with it. But overall, it's a powerful tool for staying anonymous online, as long as you use it carefully.
#### REFERENCE:
https://en.wikipedia.org/wiki/Tor_(Anonymous_network) https://resources.prodaft.com/prodaft-threat-intelligence-blog/what-is-the-tor-network-and-how-does-it-work 




# e) Don't stick that stick. How does PhishSticks attack work? Would a typical organization be vulnerable? Does this link to a broader category of attacks and defenses? How could the risk be mitigated? (This subtask does not require tests with a computer.) (If you want, you can view PhishSticks on Github and PhishSticks Youtube channel.
PhishSticks is a USB-based social engineering attack that exploits human curiosity and organizational vulnerabilities. Here's how it works:

Attackers drop USB drives in public places or near target organizations.
The drives contain malicious software disguised as legitimate files.
When an unsuspecting employee plugs in the drive, the malware executes automatically.

Many organizations remain vulnerable to this attack due to:

1. Lack of employee awareness about USB security risks.

2. Insufficient endpoint protection against autorun malware.

3. Inadequate physical security measures.

PhishSticks is part of a broader category of social engineering attacks that exploit human behavior and trust. Similar attacks include leaving infected CDs or other storage devices in public areas.

To mitigate this risk, organizations can:

1. Implement strict USB policies, disabling autorun features on all devices.

2. Conduct regular security awareness training for employees.

3. Use advanced endpoint protection solutions that can detect and block malicious USB    activities.

4. Employ physical security measures to prevent unauthorized device access.

5. Consider disabling USB ports on non-essential computers.

By combining technical controls with employee education, organizations can significantly reduce their vulnerability to PhishSticks and similar attacks.

#### REFERENCE: 
https://github.com/therealhalonen/PhishSticks/ 
https://www.youtube.com/watch?v=bDzVevtZiWE&t=23s 




