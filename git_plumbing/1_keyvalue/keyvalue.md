!SLIDE

# key/value store #

!SLIDE center
![img/AGit/get_put.017.jpg](img/AGit/get_put.017.jpg)

!SLIDE commandline incremental

	$ git init
	Initialized empty Git repository in /tmp/git-example/.git/

	$ echo 'test content' | git hash-object -w --stdin
	d670460b4b4aece5915caf5c68d12f560a9fe3e4

	$ git hash-object -w ~/README.txt
	35a0dd3af166e09ac378dfeb95953923e71ea45b

	$ git cat-file blob d670460b4b
	test content

	$ git cat-file blob 35a0dd3af166e09ac378dfeb95953923e71ea45b
	My README File
	 by Scott Chacon

	This is my README
	There are many like it
	But this one is mine

!SLIDE center
![img/AGit/key_value.019.jpg](img/AGit/key_value.019.jpg)

!SLIDE center
![img/AGit/key_value.020.jpg](img/AGit/key_value.020.jpg)

!SLIDE center
![img/AGit/key_value.021.jpg](img/AGit/key_value.021.jpg)

!SLIDE center
![img/AGit/key_value.022.jpg](img/AGit/key_value.022.jpg)

!SLIDE center
![img/AGit/key_value.023.jpg](img/AGit/key_value.023.jpg)

!SLIDE center
![img/AGit/key_value.024.jpg](img/AGit/key_value.024.jpg)

!SLIDE center
![img/AGit/key_value.025.jpg](img/AGit/key_value.025.jpg)

!SLIDE center
![img/AGit/key_value.026.jpg](img/AGit/key_value.026.jpg)

!SLIDE center
![img/AGit/key_value.027.jpg](img/AGit/key_value.027.jpg)

!SLIDE center
![img/AGit/key_value.028.jpg](img/AGit/key_value.028.jpg)

!SLIDE center
![img/AGit/key_value.029.jpg](img/AGit/key_value.029.jpg)

!SLIDE center
![img/AGit/key_value.030.jpg](img/AGit/key_value.030.jpg)

