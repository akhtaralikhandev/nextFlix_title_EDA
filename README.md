# EDA on Netflix Dataset
This project demonstrates how to perform Exploratory Data Analysis (EDA) on the Netflix dataset using PySpark in a Jupyter Notebook environment.
##  How Does it Work?

1. Install Jupyter notebook. 

2. Install Docker Desktop.

### Download The Dataset

3. Download the "Netflix Movies and TV Shows" csv file for EDA:
```
https://www.kaggle.com/datasets/victorsoeiro/netflix-tv-shows-and-movies?se
```
### Pull Jupyter pyspark notebook Image

4. Pull "jupyter pyspark notebook" image from the following command:

```
docker pull jupyter/pyspark-notebook
```

### Run the PySpark Container with VS Code Integration

5. Start the container and access the PySpark shell on a Container using Docker:

```
docker run -p 8888:8888 -p 4040:4040 -v C:\Users\user\Desktop\EDA:/home/jovyan/work --name pyspark_container jupyter/pyspark-notebook
```

6. After running this command links will be present at the end, copy it and run it on your browser. Links will look like this:

```
http://localhost:8888/?token=your-token
```

and

```
http://localhost:4040/?token=your-token
```

### Load the Dataset in pyspark in Jupyter Notebook

7. Once the dataset is accessible inside the Docker container, use the following PySpark code to load it:

```
# Import required libraries
from pyspark.sql import SparkSession

# Initialize Spark session
spark = SparkSession.builder.master("local").appName("Netflix EDA").getOrCreate()

# Load the dataset
df = spark.read.csv("/datasets/netflix.csv", header=True, inferSchema=True)
```

### Perform EDA

8. EDA is performed on the Dataset in the ipynb file uploaded.
