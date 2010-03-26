!SLIDE commandline incremental

	$ git read-tree 01d8cf040ddc3018a9f8f306ce97e20383e6faa1
	$ git ls-files
	my_readme
	test.txt
	$ ls
	$ git read-tree 0cb48f3c9538c4e43c6d102308d9dd8331f19f37
	$ git ls-files
	README.txt
	my_readme
	test.txt
	$ git checkout-index -a -f
	$ ls
	README.txt	my_readme	test.txt

!SLIDE commandline incremental

	$ vim README.txt
	$ git update-index README.txt
	$ git write-tree
	b8a266745fb81a031b81f8990b99ac7115bb2c26
	$ git cat-file -p b8a266745fb81a031b81f8990b99ac7115bb2c26
	100644 blob 289d61daa34166c8d4eddada060931	README.txt
	100644 blob 35a0dd3af166e09ac378dfeb959539	my_readme
	100644 blob d670460b4b4aece5915caf5c68d12f	test.txt

!SLIDE center
![img/CGit/index.050.jpg](img/CGit/index.050.jpg)

!SLIDE center
![img/CGit/index.051.jpg](img/CGit/index.051.jpg)

!SLIDE center
![img/CGit/index.052.jpg](img/CGit/index.052.jpg)

!SLIDE center
![img/CGit/index.053.jpg](img/CGit/index.053.jpg)

!SLIDE center
![img/CGit/index.054.jpg](img/CGit/index.054.jpg)

!SLIDE center
![img/CGit/index.055.jpg](img/CGit/index.055.jpg)

!SLIDE center
![img/CGit/index.056.jpg](img/CGit/index.056.jpg)

!SLIDE center
![img/CGit/index.057.jpg](img/CGit/index.057.jpg)

!SLIDE center
![img/CGit/index.058.jpg](img/CGit/index.058.jpg)

!SLIDE center
![img/CGit/index.059.jpg](img/CGit/index.059.jpg)

!SLIDE center
![img/CGit/index.060.jpg](img/CGit/index.060.jpg)

!SLIDE center
![img/CGit/index.061.jpg](img/CGit/index.061.jpg)

!SLIDE center
![img/CGit/index.062.jpg](img/CGit/index.062.jpg)

!SLIDE center
![img/CGit/index.063.jpg](img/CGit/index.063.jpg)

!SLIDE center
![img/CGit/index.064.jpg](img/CGit/index.064.jpg)

!SLIDE center
![img/CGit/index.065.jpg](img/CGit/index.065.jpg)

!SLIDE center
![img/CGit/index.066.jpg](img/CGit/index.066.jpg)



!SLIDE commandline incremental

	$ git read-tree 01d8cf040ddc3018a9f8f306ce97e20383e6faa1
	$ git ls-files
	my_readme
	test.txt
	$ git read-tree --prefix=sub1 01d8cf040ddc3018a9f8f306ce97e20383e6faa1
	$ git read-tree --prefix=sub2 01d8cf040ddc3018a9f8f306ce97e20383e6faa1
	$ git write-tree
	031fa9a7b8af32e9a12bd26f2bf0a0ae7bd44051
	$ git ls-files
	my_readme
	sub1/my_readme
	sub1/test.txt
	sub2/my_readme
	sub2/test.txt
	test.txt

!SLIDE commandline incremental

	$ git checkout-index -a -f
	$ tree
	my_readme
	sub1
	  `- my_readme
	  `- test.txt
	sub2
	  `- my_readme
	  `- test.txt
	test.txt
