git add .
git commit -a -m "Update from Laptop"
git push -u origin main


mkdir -p ~/hardening_cis
cd ~/hardening_cis
git clone https://github.com/kat-public/kat-rhel9-cis-custom.git .
cd cis
ansible-playbook -i inventory.ini site_ubuntu24.yml -e "@overrides_ubuntu24_cis.yml" --check
ansible-playbook -i inventory.ini site_ubuntu24.yml -e "@overrides_ubuntu24_cis.yml"