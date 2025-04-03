# DATA-1202-Final-Assignment
## Lab 6: Merging and Joining Data with Pandas
## Introduction
##### A Jupyter Notebook (lab6.ipynb) from a course on data analytics tools is available in this repository. The notebook focuses on successfully combining datasets using Pandas' merge and join abilities. I have gain hands-on expertise with inner, left, right, and exterior joins, among other merging types, by finishing this lab.
## Datasets Used
##### The notebook utilizes the following datasets:
##### Census.csv
##### licenses.csv
##### wards.csv
##### iron_1_actors
##### iron_2_actors
#### These datasets represent examples of data integration techniques, including integrating municipal data, business licenses, and demographic data.

## Key Concepts Covered
This lab covers essential Pandas operations, including:

- merge() function for different types of joins (inner, left, right, outer)

- join() function for combining DataFrames based on index

- concat() for appending DataFrames

- Handling missing values and data cleaning before merging
## Definitions
### Library
#### A collection of pre-written code that offers functionality for use in many programs is called a library. Pandas, NumPy, and Matplotlib are a few of the Python modules which make data management, numerical calculations, and visualization easier.
### Left Join
#### All records collect from the left table (table 1) and the matching records from the right table (table 2) are retrieved  values .  If there are no matching records in the right table, NULL values are included for those columns.
                                                left_join_df = pd.merge(licenses_df, wards_df, on="ward", how="left")

### Right Join
#### RIGHT JOIN returns all the rows of the table on the right side of the join and matching rows for the table on the left side of the join. 
                                                right_join_df = pd.merge(licenses_df, wards_df, on="ward", how="right")

### Outer Join
#### An outer join returns all records from both DataFrames, filling in NaN values where there is no match.
                                                outer_join_df = pd.merge(licenses_df, wards_df, on="ward", how="outer")
### code for Example
#### Loading Datasets
                                                import pandas as pd

#### Load the datasets
                                                census_df = pd.read_csv("Census.csv")
                                                licenses_df = pd.read_csv("licenses.csv")
                                                wards_df = pd.read_csv("wards.csv")

##### Display the first few rows
                                                census_df.head()
#### Merging DataFrames (Inner Join)
                                                
                                                merged_df = pd.merge(licenses_df, census_df, on="ward", how="inner")
                                                print(merged_df.head())
### Left Join Example
                                                left_join_df = pd.merge(licenses_df, wards_df, on="ward", how="left")
                                                print(left_join_df.head())
### Right Join Example
                                                right_join_df = pd.merge(licenses_df, wards_df, on="ward", how="right")
                                                print(right_join_df.head())
### outer join Example
                                                outer_join_df = pd.merge(licenses_df, wards_df, on="ward", how="outer")
                                                print(outer_join_df.head())
### Using join() for Index-based Merging
                                                  licenses_df.set_index("ward", inplace=True)
                                                  wards_df.set_index("ward", inplace=True)
                                                  
                                                  joined_df = licenses_df.join(wards_df, how="inner")
                                                  print(joined_df.head())
### Concatenating DataFrames
                                                  iron_actors_1 = pd.DataFrame({'actor': ['Robert Downey Jr.', 'Gwyneth Paltrow'], 'movie': ['Iron Man', 'Iron Man']})
                                                  iron_actors_2 = pd.DataFrame({'actor': ['Don Cheadle', 'Scarlett Johansson'], 'movie': ['Iron Man 2', 'Iron Man 2']})
                                                  
                                                  all_actors = pd.concat([iron_actors_1, iron_actors_2])
                                                  print(all_actors)
## Getting Started

### Prerequisites

Before running the notebook, ensure you have the following installed:

- Python 3.x

- Jupyter Notebook

- Pandas

- NumPy
## Installing

To set up the environment, follow these steps:

Clone this repository:
                                                   
                                                    git clone https://github.com/yourusername/your-repository.git
Navigate to the project directory:
                                                    cd your-repository
Install the required dependencies:
                                                    pip install -r requirements.txt
Launch Jupyter Notebook
                                                    jupyter notebook
## Executing the Tests

### Breakdown of Tests

This notebook includes practical tasks that confirm various merge types. Users are urged to:

- Modify the values in the dataset and see how joins impact the outcomes.

- Try combining various important columns.

- Effectively manage missing data
## Deployment
#### This project can be modified to include automated data integration pipelines, however it is intended for local execution using a Jupyter Notebook.
## Author

 Monika Sharma
## License

This project is licensed under the MIT License

## Acknowledgement

Special thanks to the instructors and peers who provided valuable feedback and guidance throughout this project.











