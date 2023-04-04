## General Description:

## Instalation:
- instalation: https://www.jenkins.io/doc/book/installing/linux/
```
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
$ sudo apt update
$ sudo apt install openjdk-11-jre
$ java -version
openjdk version "11.0.12" 2021-07-20
OpenJDK Runtime Environment (build 11.0.12+7-post-Debian-2)
OpenJDK 64-Bit Server VM (build 11.0.12+7-post-Debian-2, mixed mode, sharing)
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
curl http://127.0.0.1:8080
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
- setup username: pm1990/Mugin1990! & 
- how to setup language for Jenkins: https://superuser.com/questions/879392/how-force-jenkins-to-show-ui-always-in-english
- Jenkins token:  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

## Problem with connection:
sudo ufw disable
http://http://a83f385e432c.mylabserver.com:8080/

## Setup Project:
- Jenkins pipline steps: https://www.jenkins.io/doc/book/pipeline/

## Using env with Jenkins:
- https://www.cleanwinner.com/2020/04/12/jenkins-with-withpythonenv/ (found on net)
- Bogdan way:
                      sh ```
                            python3 -m venv ${WORKSPACE}/.venv_${BUILD_NUMBER}
                            echo ${WORKSPACE}/.venv_${BUILD_NUMBER}
                            . ${WORKSPACE}/.venv_${BUILD_NUMBER}/bin/activate
                            python3 -m pip install --upgrade pip
                            pip install --quiet -r ${WORKSPACE}/dev/django-k8s/web/requirements.txt
                        ```
- and then in each script exacute: `. ${WORKSPACE}/.venv_${BUILD_NUMBER}/bin/activate`
