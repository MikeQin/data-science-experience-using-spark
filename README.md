# Data Science Experience Using Spark on Jupyter Notebook

"Data Science Experience Using Spark" is a workshop-type of learning experience. Upon completion, you will be able to:

- Understand Jupyter Notebook App
- Learn Basic knowledge of Python
- Learn How to Use Jupyter Notebook to Run Spark Applications
- Learn Spark Basics
- Use Spark to Solve Basic Analytical Problems
- Learn How to Create RDD and DataFrame in Spark
- Learn Data Visualization Using Pandas
- Perform Machine Learning Using Spark ML

There are two parts:

- Installation
- Workshops in Python Language:
  * Spark Basics
  * Spark SQL
  * Spark Machine Learning (ML)
  
## Installation

The Installation instructions target Windows 7 OS. If you have Windows 10 OS, it's very similar. You should be able to do the same.

### Install Java JDK

If your computer already has JDK 1.8 or above installed, you can skip this step. Otherwise, please download Oracle 64-bit JDK [here](http://www.oracle.com/technetwork/java/javase/downloads/index.html), and install it using the default.

Please note, ideally your computer should have a single JDK installed. Multiple JDKs might cause some unexpected issues.

As you can see later in this document, your `JAVA_HOME` environment variable should be set to the correct JDK path. This is very important.

### Install Anaconda (Python & Jupyter Notebook)

For new users, we highly recommend installing Anaconda. Anaconda conveniently installs Python, the Jupyter Notebook, and other commonly used packages for scientific computing and data science.

Use the following installation steps:

 1. Download [Anaconda](https://www.continuum.io/downloads). I recommend downloading Anaconda’s Python 2.7 version (currently Python 3.5).

 2. Install the version of Anaconda which you downloaded, following the instructions on the download page.
  Please note, the installation folder: `C:\Programs\Anaconda2`, for example

 3. Congratulations, you have installed Jupyter Notebook.

### Verify Jupyter Notebook Installation

 To run the notebook:
  
 - Option 1: (Windows 7) Start -> All Programs -> Anaconda2 -> Jupyter Notebook
 - Option 2: In CMD window, 'cd' to a folder, such as `C:\workspace`, then run command: `jupyter notebook`. Alternatively, run command:  `pyspark` Please note, that if you run `jupyter notebook` command from a root, such as `C:\`, you will get a `404 Page Not Found` error. Basically, you can start Jupyter Notebook in any arbitrary sub-directory other than the root, you'll be fine.
 
![jupyter-01](https://github.com/MikeQin/data-science-experience-using-spark/blob/master/docs/jupyter-01.jpg)

### Install Spark

Download Apache Spark [here](http://spark.apache.org/downloads.html). I downloaded `spark-2.1.0-bin-hadoop2.7` version.

Unzip it, and copy `spark-2.1.0-bin-hadoop2.7` folder to `C:\Programs\`

Configure Spark:

1. Go into your spark/conf folder and rename log4j.properties.template to log4j.properties
2. Open log4j.properties in a text editor and change log4j.rootCategory to WARN from INFO

### Install winutils.exe for Spark

In Windows, winutils.exe is required to run Spark-Shell. Downloaded winutils.exe 64-bit version [here](https://github.com/steveloughran/winutils/raw/master/hadoop-2.6.0/bin/winutils.exe)

Create a hadoop folder on your hard drive, for example:

`C:\Programs\hadoop\bin`

Copy `winutils.exe` into `C:\Programs\hadoop\bin`

### Set Windows Environment Variables

```
JAVA_HOME=C:\Program Files\Java\jdk1.8.0_111
HADOOP_HOME=C:\Programs\hadoop
SPARK_HOME=C:\Programs\spark-2.1.0-bin-hadoop2.7
PYSPARK_DRIVER_PYTHON=jupyter
PYSPARK_DRIVER_PYTHON_OPTS=notebook
PYTHONPATH=%SPARK_HOME%/python;%SPARK_HOME%/python/lib/py4j-0.10.4-src.zip;C:\Programs\Anaconda2
Path=%Path%;%JAVA_HOME%\bin;%HADOOP_HOME%\bin;%SPARK_HOME%\bin;%PYTHONPATH%
```
You can set the above Environment Variables as `System Environment Variables` permanently in Windows. Alternatively, you can create a `setEnv.bat` file, and run it to initialize your CMD shell every time.

Please note that the `Environment Variables'` values contain software specific version numbers. It's for reference only. You shall adjust it to your own environment accordingly.

### Grant `tmp\hive` Folder Full Permission (777) for Spark

Now you need to grand permission to \tmp\hive folder using winutils

`winutils.exe chmod 777 \tmp\hive`

Check permission after grant

`winutils.exe ls \tmp\hive`

Additionally, I recommend to grant `C:\Users\[YourUserName]\AppData\Local\Temp` folder full permission (777) for Spark to delete `spark-temp` folder upon exit.

`winutils.exe chmod 777 C:\Users\[YourUserName]\AppData\Local\Temp`

### Verify Spark Installation

In CMD window, 

`spark-submit --version`

![spark-shell-03](https://github.com/MikeQin/data-science-experience-using-spark/blob/master/docs/spark-shell-03.jpg)

`spark-shell`

![spark-shell-01](https://github.com/MikeQin/data-science-experience-using-spark/blob/master/docs/spark-shell-01.jpg)

`(0 to 1).toDS.show`

![spark-shell-02](https://github.com/MikeQin/data-science-experience-using-spark/blob/master/docs/spark-shell-02.jpg)

`:q` to quit from `scala>` shell.

## Workshops in Python Language

After adding/loading a notebook module into Jupyter, and before you can run any Python Spark code, you can initialize Spark Context like this (below) if it's not being initialized:

```
# Initializing PySpark
from pyspark import SparkConf, SparkContext

# Spark Config
conf = SparkConf().setAppName("sample_app")
sc = SparkContext(conf=conf)
```

Here is how a Notebook (Lab) looks like:

![jupyter-02](https://github.com/MikeQin/data-science-experience-using-spark/blob/master/docs/jupyter-02.jpg)

### Spark Basics

Donwload the Notebook file 'Spark Basics (Lab)' [here](https://github.com/MikeQin/data-science-experience-using-spark/blob/master/notebooks/1.%20Spark%20Basics%20(Lab).ipynb).

### Spark SQL

Donwload the Notebook file 'Spark SQL (Lab)' [here](https://github.com/MikeQin/data-science-experience-using-spark/blob/master/notebooks/2.%20Spark%20SQL%20(Lab).ipynb).

### Spark Machine Learning (ML)

Donwload the Notebook file 'Spark Machine Learning (ML) (Lab)' [here](https://github.com/MikeQin/data-science-experience-using-spark/blob/master/notebooks/3.%20Spark%20Machine%20Learning%20(Lab).ipynb).
