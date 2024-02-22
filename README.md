# 🔖 TidyTuesday for Python
## JSON Nested Data of TidyTuesday Projects in 2023-2024

- **HuggingFace Dataset Homepage**: https://huggingface.co/datasets/hollyyfc/tidytuesday_for_python
- **GitHub Data Repo**: https://github.com/hollyyfc/tidytuesday-for-python.git

This dataset scrapes TidyTuesday datasets from 2023-2024, aiming to make resources in the R community more accessible for Python users. TidyTuesday, a project rooted in the R community, provides weekly datasets for data visualization and wrangling. The datasets are well-formatted (in .csv, .json, and common data file types easily accessible by all users), cleaned, and pre-wrangled by experts, but usually not first-hand information for Python learners to practice. Therefore, the initiative attempts to bridge the resource gap between R and Python communities, fostering shared educational learning and open-source collaboration. This collection includes metadata like date posted, project name, source, description, data dictionaries, data download URLs, and project post repo URLs, and the language used is mainly English. 

*Note: As a pilot project, the datasets from Tidy Tuesday will be added retrospectively. The baseline is to add all information starting from Jan 2023. Depending on time and availability, data dating back further will also be considered.*

## Dataset Details

### Dataset Description

- **Curated by:** Holly Cui @[hollyyfc](https://hollyyfc.github.io/)
- **Language(s) (NLP):** English

### Dataset Sources

- **Repository:** https://github.com/rfordatascience/tidytuesday/tree/master

## Uses

- This dataset can be used for data visualization, statistical analysis, and machine learning NLP tasks. Since it's a compilation of diverse datasets, it supports a variety of tasks and can be used to benchmark different data processing and visualization techniques in Python.
- This dataset can also be your starting point in discovering various topics of exploration, stepping your feet into unknown territories, and offering insights into the impact that data can realize. Direct view and download links are provided within the data structure. 
- By referring to TidyTuesday, you have the ability to discover the specialties of both Python and R, choose wisely on different packages or features that each language offers, or even learn a new language based on the one you’re familiar with!

## Dataset Structure

The dataset is stored in both JSON nested hierarchical structure and CSV format. 

- Full set: `tidytuesday_json.json` and `tidytuesday_2023_2024.csv`
- Train set: `tidytuesday_json_train.json` and `tidytuesday_train.csv`
- Validation set: `tidytuesday_json_val.json` and `tidytuesday_val.csv`

### Data Instances

```python
{
    "date_posted": "YYYY-MM-DD",
    "project_name": "Example project name for one post",
    "project_source": ["https://example-tidytuesday-post-source/", ...],
    "description": "Project description excerpted from TidyTuesday repo",
    "data_source_url": "https://example-tidytuesday/date/repo",
    "data_dictionary": [
        {
            "variable": [variable1, variable2, ...],
            "class": [class_type1, class_type2, ...],
            "description": ["Description of var1", "Description of var2", ...]
        },
        ...
    ],
    "data": {
        "file_name": [
            "data1.csv", 
            "data2.csv", 
            ...
            ],
        "file_url": [
            "https://example-tidytuesday/view-link-to-data1", 
            "https://example-tidytuesday/view-link-to-data2", 
            ...
            ]
    },
    "data_load": {
        "file_name": [
            "data1.csv", 
            "data2.csv", 
            ...
            ],
        "file_url": [
            "https://example-tidytuesday/download-link-to-data1", 
            "https://example-tidytuesday/download-link-to-data2", 
            ...
            ]
    }
}
```

### Data Fields

- `date_posted`: The date when the weekly project was posted *(YYYY-MM-DD str)*.
- `project_name`: The name of the weekly project *(str)*.
- `project_source`: A list of URLs to the project's data and information source *(List[str])*.
- `description`: A brief excerpt of the project and dataset description *(str)*.
- `data_source_url`: The URL to the weekly project repository *(str)*.
- `data_dictionary`: A list of dictionaries, each containing the variable names, classes, and descriptions for each dataset *(List[Dict[str: List[str]]])*. 
- `data`: A dictionary of dataset names and links to view. The values of the keys `file_name` and `file_url` are organized in list fashion. 
- `data_load`: A dictionary of dataset names and links to direct download. The values of the keys `file_name` and `file_url` are organized in list fashion *(Dict[str: List[str]])*. 

## Dataset Creation

### Curation Rationale

The genesis of this dataset was rooted in a personal quest to bridge the gap between the R and Python communities, particularly in the realm of data visualization and wrangling. As an avid data enthusiast, I often encountered challenges in discovering captivating projects and datasets to fuel my own analytical endeavors. Tidy Tuesday, with its weekly release of diverse and engaging datasets, presented a goldmine of opportunities. However, I noticed a disconnect - these datasets, predominantly tailored for the R community, were not as readily accessible or structured for Python users. This realization sparked the ambition to create a centralized, Python-friendly repository of TidyTuesday's 2023 datasets. By doing so, the dataset aims to democratize access to these rich resources, fostering a shared learning environment and stimulating innovation across both R and Python communities.

The dataset has been crafted to include essential metadata like the date posted, project name, data source, and a comprehensive description. What makes it stand out is the inclusion of a nested data structure for both the data dictionary and the actual data, tailored to enhance user experience and accessibility. This structure not only addresses the challenges I faced in finding and utilizing interesting datasets for personal projects but also streamlines the process for others facing similar hurdles. The ultimate goal is to create a vibrant, interactive playground where enthusiasts from both communities can converge, collaborate, and contribute, thereby enriching the data science landscape with diverse perspectives and insights.

### Source Data

The major source of data is directly from the [TidyTuesday](https://github.com/rfordatascience/tidytuesday) official site. Initial data collection and normalization were conducted collaboratively by the organizers of Tidy Tuesday and data runners within the R community. Since it is an R-oriented initiative, the source language, example files, and authors' dataset cleanings were mostly done in R.

#### Who are the original source data producers?

The source data come from a variety of fields, including but not limited to the R community, TidyTuesday collaborators, interesting web postings, and scholarly papers. Details of each week's data sources can be retrieved from the `project_source` variable. Descriptions of the sources can also be found as part of the `description` variable. 

### Data Collection and Processing

The data collection process involved several key stages, starting with the use of Python libraries `requests` and `BeautifulSoup` to programmatically navigate the repository and extract post dates and URLs for selected years. This initial step was crucial for mapping out the structure of the data collection effort.

Subsequent to this foundational step, detailed scraping scripts were developed to delve into individual post URLs, extracting the variable-specific information. Special attention was paid to the HTML structure of the TidyTuesday posts to ensure accurate and efficient data extraction. This process was iterative and adaptive, with scripts being refined to handle inconsistencies in post structures and to ensure comprehensive data capture.

The resultant dataset is presented in both CSV and JSON formats, providing flexibility for analysis and application. The JSON format, in particular, was structured to facilitate easy integration into Python environments, with nested objects and hierarchical data representations designed for intuitive access and manipulation. This meticulous approach to data collection and processing ensures that the dataset is not only comprehensive and detailed but also ready for immediate use in a wide range of data analysis, machine learning, and data visualization projects. The full dataset, along with subsets for training and validation, has been made available here on GitHub, ensuring open access for researchers, data scientists, and enthusiasts interested in exploring social data trends. My [cleaning and preprocessing codebook](https://github.com/hollyyfc/tidytuesday-for-python/blob/94a9dae648600d890aa346b6b339281d0e15ec64/huggingface_preprocessing.ipynb) can also be retrieved.

#### Personal and Sensitive Information

Due to the open-source nature of TidyTuesday, the data and information provided in this dataset will not encounter sensitivity issues. However, any links and datasets will be double-checked to ensure compliance with the regulations. 

## Considerations for Using the Data

### Social Impact of Dataset

This dataset, which amalgamates TidyTuesday 2023-2024 datasets into a Python-friendly format, is designed to have a social and educational impact on the data science community. By making these datasets more accessible to Python users, it fosters a more inclusive and diverse analytical environment. The initiative encourages cross-community collaboration and learning, breaking down barriers between R and Python practitioners. This aids in skill development and knowledge sharing but promotes a culture of open-source contribution. In providing a variety of datasets from different domains, this collection serves as a launchpad for innovative projects and analyses, potentially leading to new insights and discoveries that can benefit various fields. However, it's important to consider the impact of this data when used for decision-making, as insights drawn from it could influence societal perceptions and actions in diverse sectors.

### Discussion of Biases

While the dataset serves as a rich resource, it's crucial to acknowledge the potential biases inherent in its composition. The TidyTuesday project, primarily driven by contributions and selections from the R community, may reflect the interests and perspectives of its contributors, which might not fully represent the broader data science community. This can lead to certain topics or domains being overrepresented while others are underrepresented. Users should be mindful of these biases when drawing conclusions or generalizations from analyses conducted on this dataset. It's advisable to use this dataset in conjunction with other sources to ensure a more balanced and comprehensive view of the subject matter at hand.

### Other Known Limitations

One of the known limitations of this dataset is its dependency on the nature and structure of the original TidyTuesday datasets. Since these datasets are curated for weekly challenges, they might not always be comprehensive or suitable for all types of analytical tasks. Additionally, the dataset's structure, with nested dataframes, while beneficial for accessibility and ease of use, may present challenges in certain types of data processing or analysis tasks. Users should be aware of these limitations and consider them when choosing this dataset for their specific needs or projects. Moreover, as the dataset is a compilation of weekly releases from 2023, it may not include the most up-to-date data or cover trends and topics beyond this period.


## Dataset Contact

Holly Cui ([Email](mailto:yifan.cui@duke.edu) | [Website](https://hollyyfc.github.io/) | [GitHub](https://github.com/hollyyfc))
