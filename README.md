# 🧹 Remove .DS\_Store Files (macOS)

This repository contains a simple **Zsh script** to remove hidden `.DS_Store` files that macOS automatically creates in your project folders.
Normal on macOS, but these files are unnecessary for development projects and can clutter repositories if accidentally committed.

---

## 🚀 How to Use

### 1. Open Terminal

```zsh
open -a Terminal
```

### 2. Create a new folder and go inside it

```zsh
mkdir new-folder
cd new-folder
```

### 3. Create the script file

```zsh
touch remove-hidden-files.sh
```

### 4. Edit the script

```zsh
nano remove-hidden-files.sh
```

### 5. Paste this code into the file

```zsh
#!/bin/zsh

TARGET_DIR="/Users/yourname/your-project-folder"  # <-- change this to your project folder path

if [ ! -d "$TARGET_DIR" ]; then
  echo "Error: Target directory does not exist."
  exit 1
fi

find "$TARGET_DIR" -name ".DS_Store" -type f -print -delete

echo "All .DS_Store files removed from $TARGET_DIR"
```

Save with **CTRL+O** → press **Enter** → then exit with **CTRL+X**.

---

### 6. Make the script executable

```zsh
chmod +x remove-hidden-files.sh
```

### 7. Run the script

```zsh
./remove-hidden-files.sh
```

---

## ✅ Example Output

```
/Users/yourname/your-project-folder/.DS_Store
All .DS_Store files removed from /Users/yourname/your-project-folder
```

---

## 📝 Notes

* Be sure to change `TARGET_DIR` to the path of your actual project folder.
* To avoid committing `.DS_Store` to Git, add it to your `.gitignore` file:

  ```zsh
  echo ".DS_Store" >> .gitignore
  git rm --cached .DS_Store
  ```
* You can remove any hidden files using this method, just replace `.DS_Store` with the name of the hidden file you want to delete.
* That’s it 🎉 Your project will now stay clean from unnecessary macOS files.

