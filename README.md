# ops-beliven-test

Il testo dell'esercizio da eseguire è il seguente:

1. Creare una VM su Hetzner (taglio più piccolo "cx11") con Terraform. Consiglio di utilizzare Ubuntu 22.04. Ricordarsi di inserire una propria chiave SSH, altrimenti sarà impossibile procedere con lo step 2.
   Inoltre, è necessario ricordarsi di stampare come output l'IPv4 della VM, altrimenti non si avrà evidenza dell'IP della VM per procedere con lo step 2 (vedere documentazione su "output" Terraform). Questo è il token API da configurare su Terraform per poter creare risorse all'interno del nostro account Hetzner (abbiamo creato un progetto dedicato a te): **\_\_\_**
2. Creare un playbook Ansible per configurare la VM appena creata, nel farlo utilizzare le seguenti role:
   - firewall ufw - https://github.com/Oefenweb/ansible-ufw
   - fail2ban - https://github.com/Oefenweb/ansible-fail2ban
   - unattended upgrades - https://github.com/jnv/ansible-role-unattended-upgrades
3. Bonus: Configurare a mano utente SFTP per poter caricare i file di Laravel tramite SFTP, Nginx (con proxy pass su PHP-FPM per i file php), PHP-FPM e MySQL (attenzione a configurare i permessi di php-fpm in modo corretto, in modo che coincidano con l'utente SFTP che carica i file di Laravel).

## Terraform Available Scripts

1. Add the missing values to `terraform.tfvars.json`

- `terraform init`
- `terraform fmt`
- `terraform validate`
- `terraform apply`
- `terraform destroy `

## Ansible Available Scripts

1. Run `ansible-galaxy install -r requirements.yml --force`
2. Open `hosts.yml` file and replace the placeholders with correct values

- `ansible all -m ping`
- `ansible all -a "/bin/echo hello"`
- `ansible-playbook -i hosts.yml playbook.yml --ask-vault-pass`
- `ansible-playbook playbook.yml`
- `openssl passwd -1 -salt passpass`
