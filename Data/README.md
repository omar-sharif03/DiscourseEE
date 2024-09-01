## 📝 File Description
The `final-data.json` file contains all the annotations, while `train.json`, `dev.json`, and `test.json` include the training, validation, and test splits, respectively. The `role-descriptions` file contains short descriptions of each event roles. Each of these files is structured as a list of dictionaries. They keys of the dictionary are:
* `doc_id`: unique document id indicating the annotator.
* `id`: unique id string for the sample.
* `event-label`: corresponding event of the sample. Events are *taking-moud*, *relapse*, and *tapering*.
* `post`: post from the discourse.
* `comment`:one of the corresponding comment from the discourse.
* `ground-truth-arguments`: it contains our annotations which a dictionary.
    * `argument-types`: in the dictionary, the first level is argument types *(core, type-specific, subject-effect)* arguments.
        * `role`: corresponding role values for each event and argument type.
        * `value-list`: a list of tuples where the first element is annotation and the second element mentions whether it is *explicit, implicit, or scattered*.
          
![EAE-events-arguments](https://github.com/user-attachments/assets/3601aa48-a9f6-40ac-a0ed-ad8777ab20cd)

## 🧑🏻‍💻 Read the Dataset
The following instructions will show how to read and use the dataset. 

1. Clone the repository
```bash
!git clone https://github.com/omar-sharif03/DiscourseEE.git
!cd /content/DiscourseEE && git pull
```
2. Read the data files 
```python
def read_json_file(name):
    with open(name, 'r') as f:
        data = json.load(f)
        return data

folder_path = '/content/DiscourseEE/Data'
data_file_name = 'final-data.json'
role_file_name = 'role_definitions.json'

with open(os.path.join(folder_path, data_file_name), "r") as json_file:
    data = json.load(json_file)

with open(os.path.join(folder_path, role_file_name), "r") as json_file:
    events_roles = json.load(json_file)
```
3. Enummeate the data dictionary
```python
event_types = ['taking-moud', 'relapse', 'tapering']
arg_types = ['core-arguments', 'type-specific-arguments', 'subject-effect-arguments']

for dt in data[:2]: #going over 2 samples of the data file
    all_arguments = dt['ground-truth-arguments']
    print("**************")
    for arg_type in arg_types: #itreating over core, type-specific and subject-effect arguments of each event
        roles = list(all_arguments[arg_type].keys()) #getting the roles of correspoing argument type
        print("---------------")
        print(f"[{dt['event-label']}], [{arg_type}]\n{roles}\n")
        for role in roles:
            values_list = all_arguments[arg_type][role] #annotated argument list
            for value, typ in values_list:
                print(f'{role}: {value} - {typ}') #value is argument value and typ is type(explicit, implicit, scattered)
```
----
**Load the data in Google Colab** [Demo Notebook for Data Reading & Statistics](https://github.com/omar-sharif03/DiscourseEE/blob/main/Data/DiscourseEE-Data_Reading_%26_Data_Statistics.ipynb) 
