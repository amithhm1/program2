# Install Git
sudo apt update
sudo apt install git -y

# Configure Git
git config --global user.name "AMITH H M"
git config --global user.email "amithhm511@gmail.com"

# Generate SSH key
ssh-keygen -t ed25519 -C "amithhm511@gmail.com"

# Start SSH agent and add key
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Display public key (copy this and add it to GitHub → Settings → SSH and GPG keys)
cat ~/.ssh/id_ed25519.pub

# Test SSH connection (type 'yes' if prompted)
ssh -T git@github.com

# Go to your project folder
cd /path/to/your/project

# Initialize Git and push to GitHub
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin git@github.com:amithhm1/program2.git
git push -u origin main --force
