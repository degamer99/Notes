## Arch
```bash
sudo pacman -S jdk8-openjdk  # install that java version
archlinux-java status # list the available java versions
sudo archlinux-java set java-8-openjdk # set the java version to 
java -version #  openjdk version "1.8.0_402"
```

- For Windows
* Install manually
* ```cmd
  where java 
```

* for temporary change 
```powershell
set JAVA_HOME=C:\Program Files\Java\jdk1.8.0_xxx
set PATH=%JAVA_HOME%\bin;%PATH%

java -version
```

* for permanent change 
1. Press Win + R, type sysdm.cpl, hit Enter.
1. Go to Advanced → Environment Variables.
1. Under System variables, add or edit:
1. JAVA_HOME = C:\Program Files\Java\jdk1.8.0_xxx
1. Add %JAVA_HOME%\bin to the start of the Path variable.
1. Open a new terminal and run:
1. java -version
