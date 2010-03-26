!SLIDE bullets

* Simple key/value content storage system
* Directory snapshot storage system
* History of directory snapshots system

!SLIDE commandline incremental

	$ git cat-file -p 0cb48f3c9538c4e43c6d102308d9dd8331f19f37
	100644 blob 35a0dd3af166e09ac378dfeb95953923e71ea45b	README.txt
	100644 blob 35a0dd3af166e09ac378dfeb95953923e71ea45b	my_readme
	100644 blob d670460b4b4aece5915caf5c68d12f560a9fe3e4	test.txt
	$ git cat-file -p b8a266745fb81a031b81f8990b99ac7115bb2c26
	100644 blob 289d61daa34166c8d4eddada06093112ed081766	README.txt
	100644 blob 35a0dd3af166e09ac378dfeb95953923e71ea45b	my_readme
	100644 blob d670460b4b4aece5915caf5c68d12f560a9fe3e4	test.txt
	$ echo 'first commit' | git commit-tree 0cb48f3c9538c4e43c6d102308d9dd8331f19f37
	ac113b8016a4982f4d20684dc8680fa8d9abecec
	$ git cat-file -p ac113b8016a4982f4d20684dc8680fa8d9abecec
	tree 0cb48f3c9538c4e43c6d102308d9dd8331f19f37
	author Scott Chacon <schacon@gmail.com> 1269599824 -0700
	committer Scott Chacon <schacon@gmail.com> 1269599824 -0700

	first commit

!SLIDE commandline incremental

	$ echo 'second commit' | git commit-tree b8a26674 -p ac113b8016a
	b0ce9e5ecc452f282ff37340541b308f4bf2cd62
	$ git log b0ce9e5ecc452f282ff37340541b308f4bf2cd62
	commit b0ce9e5ecc452f282ff37340541b308f4bf2cd62
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Fri Mar 26 03:38:12 2010 -0700

	    second commit

	commit ac113b8016a4982f4d20684dc8680fa8d9abecec
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Fri Mar 26 03:37:04 2010 -0700

	    first commit

!SLIDE commandline incremental

	$ echo b0ce9e5ecc452f282ff37340541b308f4bf2cd62 > .git/master
	$ git log $(cat .git/master)
	commit b0ce9e5ecc452f282ff37340541b308f4bf2cd62
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Fri Mar 26 03:38:12 2010 -0700

	    second commit

	commit ac113b8016a4982f4d20684dc8680fa8d9abecec
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Fri Mar 26 03:37:04 2010 -0700

	    first commit

!SLIDE center
![img/CommitsA/commits.071.jpg](img/CommitsA/commits.071.jpg)

!SLIDE center
![img/CommitsA/commits.072.jpg](img/CommitsA/commits.072.jpg)

!SLIDE center
![img/CommitsA/commits.073.jpg](img/CommitsA/commits.073.jpg)

!SLIDE center
![img/CommitsA/commits.074.jpg](img/CommitsA/commits.074.jpg)

!SLIDE center
![img/CommitsA/commits.075.jpg](img/CommitsA/commits.075.jpg)

!SLIDE center
![img/CommitsA/commits.076.jpg](img/CommitsA/commits.076.jpg)

!SLIDE center
![img/CommitsA/commits.077.jpg](img/CommitsA/commits.077.jpg)

!SLIDE center
![img/CommitsA/commits.078.jpg](img/CommitsA/commits.078.jpg)

!SLIDE center
![img/CommitsA/commits.079.jpg](img/CommitsA/commits.079.jpg)

!SLIDE center
![img/CommitsA/commits.080.jpg](img/CommitsA/commits.080.jpg)

!SLIDE center
![img/CommitsA/commits.081.jpg](img/CommitsA/commits.081.jpg)

!SLIDE center
![img/CommitsA/commits.082.jpg](img/CommitsA/commits.082.jpg)




