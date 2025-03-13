## How to Install Anisble on Linux
1. pip install ansible

## Validate Ansible is installed
2. ansible --version 

## Installing and upgrading Ansible with pip

Locate and remember the path to the Python interpreter you wish to use to run Ansible. The following instructions refer to this Python as python3. For example, if you have determined that you want the Python at /usr/bin/python3.9 to be the one that you will install Ansible under, specify that instead of python3.

## Ensuring pip is available
To verify whether pip is already installed for your preferred Python:

python3 -m pip -V
If all is well, you should see something like the following:

python3 -m pip -V
pip 21.0.1 from /usr/lib/python3.9/site-packages/pip (python 3.9)
If so, pip is available, and you can move on to the next step.

If you see an error like No module named pip, you will need to install pip under your chosen Python interpreter before proceeding. This may mean installing an additional OS package (for example, python3-pip), or installing the latest pip directly from the Python Packaging Authority by running the following:

curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py --user
You may need to perform some additional configuration before you are able to run Ansible. See the Python documentation on installing to the user site for more information.

## Installing Ansible
Use pip in your selected Python environment to install the full Ansible package for the current user:

python3 -m pip install --user ansible
You can install the minimal ansible-core package for the current user:

python3 -m pip install --user ansible-core
Alternately, you can install a specific version of ansible-core:

python3 -m pip install --user ansible-core==2.12.3
