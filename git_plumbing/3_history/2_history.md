!SLIDE commandline incremental

	$ git log --stat --raw $(cat .git/master)
	commit b0ce9e5ecc452f282ff37340541b308f4bf2cd62
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Fri Mar 26 03:38:12 2010 -0700

	    second commit

	:100644 100644 35a0dd3... 289d61d... M  README.txt
	 README.txt |    2 +-
	 1 files changed, 1 insertions(+), 1 deletions(-)

	commit ac113b8016a4982f4d20684dc8680fa8d9abecec
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Fri Mar 26 03:37:04 2010 -0700

	    first commit

	:000000 100644 0000000... 35a0dd3... A  README.txt
	:000000 100644 0000000... 35a0dd3... A  my_readme
	:000000 100644 0000000... d670460... A  test.txt
	 README.txt |    7 +++++++
	 my_readme  |    7 +++++++
	 test.txt   |    1 +
	 3 files changed, 15 insertions(+), 0 deletions(-)
	$ git read-tree ac113b8016a4982f4d20684dc8680fa8d9abecec
	$ git checkout-index -a -f
	$ ls
	README.txt    my_readme    test.txt

!SLIDE commandline incremental

	$ vim README.txt
	$ git diff
	diff --git a/README.txt b/README.txt
	index 35a0dd3..e987eef 100644
	--- a/README.txt
	+++ b/README.txt
	@@ -3,5 +3,5 @@ My README File

	 This is my README
	 There are many like it
	-But this one is mine
	+But this one is ours

!SLIDE commandline incremental

	$ git update-index README.txt
	$ git write-tree
	2a654888e3ba2118be7c3f528c09d1b87a882d2f
	$ git cat-file -p 2a654888e3ba2118be7c3f528c09d1b87a882d2f
	100644 blob e987eef9d6915d8c3fd45f850f954b10e5504f8f	README.txt
	100644 blob 35a0dd3af166e09ac378dfeb95953923e71ea45b	my_readme
	100644 blob d670460b4b4aece5915caf5c68d12f560a9fe3e4	test.txt
	$ git cat-file -p e987eef9d6915d8c3fd45f850f954b10e5504f8f
	My README File
	 by Scott Chacon

	This is my README
	There are many like it
	But this one is ours

!SLIDE commandline incremental

	$ echo 'third commit - ours' | git commit-tree 2a654888 -p ac113b8
	f425053ff8d53c5b64410cf9bab994d45ac7c711
	$ git log f42505
	commit f425053ff8d53c5b64410cf9bab994d45ac7c711
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Fri Mar 26 03:44:08 2010 -0700

	    third commit - ours

	commit ac113b8016a4982f4d20684dc8680fa8d9abecec
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Fri Mar 26 03:37:04 2010 -0700

	    first commit
	$ echo 'f425053ff8d53c5b64410cf9bab994d45ac7c711' > .git/ours

!SLIDE commandline incremental

	$ git log --graph $(cat .git/master) $(cat .git/ours)
	* commit f425053ff8d53c5b64410cf9bab994d45ac7c711
	| Author: Scott Chacon <schacon@gmail.com>
	| Date:   Fri Mar 26 03:44:08 2010 -0700
	|
	|     third commit - ours
	|
	| * commit b0ce9e5ecc452f282ff37340541b308f4bf2cd62
	|/  Author: Scott Chacon <schacon@gmail.com>
	|   Date:   Fri Mar 26 03:38:12 2010 -0700
	|
	|       second commit
	|
	* commit ac113b8016a4982f4d20684dc8680fa8d9abecec
	  Author: Scott Chacon <schacon@gmail.com>
	  Date:   Fri Mar 26 03:37:04 2010 -0700

	      first commit

!SLIDE commandline incremental

	$ git read-tree $(cat .git/master)
	$ git checkout-index -a -f
	$ tail README.txt
	My README File
	 by Scott Chacon

	This is my README
	There are many like it
	But this one is yours

	$ git read-tree $(cat .git/ours); git checkout-index -a -f
	$ cat README.txt
	My README File
	 by Scott Chacon

	This is my README
	There are many like it
	But this one is ours

!SLIDE center
![img/CommitsB/commits.084.jpg](img/CommitsB/commits.084.jpg)

!SLIDE center
![img/CommitsB/commits.085.jpg](img/CommitsB/commits.085.jpg)

!SLIDE center
![img/CommitsB/commits.086.jpg](img/CommitsB/commits.086.jpg)

!SLIDE center
![img/CommitsB/commits.087.jpg](img/CommitsB/commits.087.jpg)

!SLIDE center
![img/CommitsB/commits.088.jpg](img/CommitsB/commits.088.jpg)

!SLIDE center
![img/CommitsB/commits.089.jpg](img/CommitsB/commits.089.jpg)

!SLIDE center
![img/CommitsB/commits.090.jpg](img/CommitsB/commits.090.jpg)

!SLIDE center
![img/CommitsB/commits.091.jpg](img/CommitsB/commits.091.jpg)

!SLIDE center
![img/CommitsB/commits.092.jpg](img/CommitsB/commits.092.jpg)

!SLIDE center
![img/CommitsB/commits.093.jpg](img/CommitsB/commits.093.jpg)

