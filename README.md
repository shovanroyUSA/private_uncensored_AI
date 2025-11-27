# private_uncensored_AI
Create private uncensored AI, which will not share your data to the internet. Its free to use and safe. 
## 1. Intstall Ubuntu
- From windows command prompt-> wsl --install
- Create a default Unix user account: shovan
- New password: sh.....98
- Retype new password:
- Update apt-> sudo apt update

## 2. Install Ollama
- Go to https://ollama.com/download/linux <img width="634" height="398" alt="image" src="https://github.com/user-attachments/assets/7ec8579e-fdef-43b4-a9c3-6aa0f8af44f2" />
- Copy the command and run it to the terminal -> curl -fsSL https://ollama.com/install.sh | sh
- Go to the models and choose a model:  copy the model name (llama3.1:8b) <img width="776" height="471" alt="image" src="https://github.com/user-attachments/assets/dc59db8c-e7d6-41f4-bd59-cef718228ba2" />
- Pull the model: -> ollama pull llama3.1:8b
- Run the model: -> ollama run llama3.1:8b
- To Exit type: /bye 

## 3. Install Docker: Install Docker Engine on Ubuntu
- Check your OS: -> cat /etc/os-release
- Install using the apt repository: <img width="677" height="461" alt="image" src="https://github.com/user-attachments/assets/381cc1b7-6995-4f81-a795-4b7678846fbb" />
- Insatll docker package:-> sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

## 4. Install Interface: Open Web UI
- Go to Open Web Ui <img width="677" height="461" alt="image" src="https://github.com/user-attachments/assets/adc5031f-c0a3-4eea-9f40-b8476aad6906" />
- Run the code: -> sudo docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
- Open a new tab and type: http://localhost:8080 <img width="608" height="446" alt="image" src="https://github.com/user-attachments/assets/b503dc0a-f05a-451d-923a-455417d7b1e9" />
- Open Web UI interface: <img width="602" height="362" alt="image" src="https://github.com/user-attachments/assets/664ac7fd-3072-4fb3-911e-fc49d6b8cdd5" />
- Here is your personal AI with chat Interface
- !Unable to run the model due to my RAM constraint. Model size is 4.8GB, however my remaining RAM size is 3.3 GM, unable to load the model into my RAM.

## 5. How to re-run it after closing?
- open terminal: -> wsl
- -> ollama serve
- sudo docker start open-webui

## 6. Install another model tinydolphin:1.1b 
- As we have memory constraint, we want to work with tiny models: <img width="712" height="358" alt="image" src="https://github.com/user-attachments/assets/8d38bb22-e787-4d13-bf63-54eb89d24fe6" />
-  -> ollama pull tinydolphin:1.1b
-  ollama run tinydolphin:1.1b
- To open chat interface: localhost:8080 <img width="921" height="467" alt="image" src="https://github.com/user-attachments/assets/e883a21d-8e32-41fd-92d6-5e649f5c2e5b" />
- This is a uncensored and private model running on your own device. Have fun.

## 7. Clean Up
- Stop the container: -> sudo docker stop open-webui
- Remove Open Web UI: -> sudo docker rm open-webui
- Remove volume: -> sudo docker rm volume open-webui
- Remove Image: -> sudo docker rmi ghcr.io/open-webui/open-webui:main
- Uninstall Docker: -> sudo apt purge docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-ce-rootless-extras
- sudo rm -rf /var/lib/docker
- sudo rm -rf /var/lib/containerd
- sudo rm /etc/apt/sources.list.d/docker.sources
- sudo rm /etc/apt/keyrings/docker.asc
### Uninstall Ollama
 - sudo systemctl stop ollama
 - sudo systemctl disable ollama
 - sudo rm /etc/systemd/system/ollama.service
### Remove the downloaded models 
 - sudo userdel ollama
 - sudo groupdel ollama
 - sudo rm -r /usr/share/ollama
  
### Ungerister Ubuntu
- -> wsl --unregister Ubuntu
- Uninstall wsl
- -> wsl --uninstall






