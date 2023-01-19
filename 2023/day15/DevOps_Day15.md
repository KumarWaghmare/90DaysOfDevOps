# **Day 15 — Python Libraries for DevOps**
## Tasks:

### **1. Create a Dictionary in Python and write it to a json File.**

To create a dictionary in Python and write it to a json file, you can use the json module:
![011](https://user-images.githubusercontent.com/121767243/213429645-b0df92a3-0f90-428b-a0dd-f3c6f895929a.png)


### **2. Read a json file services.json kept in this folder and print the service names of every cloud service provider.**
```
output

aws : ec2
azure : VM
gcp : compute engine
```
To read a json file and print the service names of every cloud service provider, you can use the json module again:
![022](https://user-images.githubusercontent.com/121767243/213429684-6ab65d5e-7d6b-4c7b-9909-9182e38a6cea.png)

Make sure that the file ‘services.json’ is in the same folder as the python file you created, otherwise you’ll get a file not found error when trying to read the json file.

### **3. Read YAML file using python, file services.yaml and read the contents to convert yaml to json.**
To read a YAML file using python and convert it to json, you will need to install the PyYAML library:
```
pip3 install pyyaml
```
Then use the yaml and json modules to read the YAML file and convert it to json
```
import yaml
import json

# read the YAML file
with open("services.yaml", "r") as f:
    yaml_data = yaml.safe_load(f)

# convert the YAML data to json
json_data = json.dumps(yaml_data)

# write the json data to file
with open('services.json', 'w') as f:
    json.dump(json_data, f)
 ```
