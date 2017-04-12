# Data Science Experience Using Spark

"Data Science Experience Using Spark" is a workshop-type of learning experience. Upon completion, you will be able to:

- Understand Jupyter Notebook App
- Gain basic knowledge of Python
- Know how to use Jupyter Notebook to run Spark applications
- Learn Spark basics
- Use Spark to solve basic analytical problems
- Know how to create RDD and DataFrame in Spark
- Perform Machine Learning using Spark ML

There are two parts:

- Installation
- Workshops:
  * Spark Basics
  * Spark SQL
  * Spark Machine Learning (ML)
  
## Installation

The target OS for this workshop is Windows 7, 10.

### Install Java JDK

Download Oracle JDK [here](http://www.oracle.com/technetwork/java/javase/downloads/index.html), and install it using the default.

### Install Anaconda

For new users, we highly recommend installing Anaconda. Anaconda conveniently installs Python, the Jupyter Notebook, and other commonly used packages for scientific computing and data science.

Use the following installation steps:

  1. Download [Anaconda](https://www.continuum.io/downloads). I recommend downloading Anaconda’s Python 2.7 version (currently Python 3.5).

  2. Install the version of Anaconda which you downloaded, following the instructions on the download page.
  Please note, the installation folder: `C:\Programs\Anaconda2`, for example

  3. Congratulations, you have installed Jupyter Notebook. To run the notebook:
  
  ``` 
  jupyter notebook
  ```

### Install Spark

Download Apache Spark [here](http://spark.apache.org/downloads.html). I downloaded `spark-2.1.0-bin-hadoop2.7` version.

Unzip it, and copy `spark-2.1.0-bin-hadoop2.7` folder to `C:\Programs\`

### Install winutils.exe

In Windows, winutils.exe is required. winutils.exe can be downloaded 64-bit version [here](https://github.com/steveloughran/winutils/raw/master/hadoop-2.6.0/bin/winutils.exe)

Create a hadoop folder on your hard drive, for example:

`C:\Programs\hadoop\bin`

Copy `winutils.exe` into `C:\Programs\hadoop\bin`

### Grant `tmp\hive` Folder Full Permission (777)

Now you need to grand permission to \tmp\hive folder using winutils

`winutils.exe chmod 777 \tmp\hive`

Check permission after grant

`winutils.exe ls \tmp\hive`

Additionally, I recommend to grant `C:\Users\[YourUserName]\AppData\Local\Temp` folder full permission (777) for Jupyter Notebook App to delete `spark-temp` folder upon exit.

`winutils.exe chmod 777 C:\Users\[YourUserName]\AppData\Local\Temp`

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

## Workshops

### Spark Basics

### Spark SQL

### Spark Machine Learning (ML)
