#REQUIREMENT : 
Create 3 objects: object A , Object B, Object C,

- C with lookup field to B

- B with lookup field to A

- Create record page for object A and add a lightning component to show a custom related list where it shows a table with all records of object B and C without any distinction
- Needs to be scalable for a huge number of records and don't forget limits. You can use pagination or infinite scrolling, as you prefer.
- To deliver: package ready to be deployed with all metadata that you created

# we will use Aura cmp with Lightning Related List Filter

This solution is a lightning component which mimimic the look and feel with the out of box related list but give you more control on:

1. You can apply filter of your choice on the related list.
2. You are not limited to child object but any grand-child object as long as it can reference back to the parent.
3. You can specify the title of the related list that is meaningful to you.
4. You are not limited to only four fields to show.
5. You are not limited to 6 records but have more control on how many records you want to show,
6. You don't have to show the ugly bar code for you child object.
7. You can choose from display types of List or Tile.

we can now add Related list on Object A record page that will contain a table of related object B and object C.


#### Currently the related list supports the following field type:
1. Text
2. Number
3. Percent
4. Date
5. Datetime
6. Checkbox
7. Picklist
8. Muti-picklist
9. Lookup
10. Master-Detail
11. Email
12. Phone
13. URL

## Getting Started
### If you are using sfdx
1. Clone this repo
```
git clone https://github.com/libra34567/lightningRelatedListWithFilter.git
```
2. Direct to the root
```
cd lightningRelatedListWithFilter/
```
3. Deploy to your desired org
```
sfdx force:source:deploy -p sf_relatedList -u $YOURORGNAME
```

### If you are using meta-data
1. Clone this repo
```
git clone https://github.com/libra34567/lightningRelatedListWithFilter.git
```
2. Direct to the root/package
```
cd lightningRelatedListWithFilter/package
```
3. Ant deploy the package
```
 
```


## How to use the related list on your lightning record page
1. Navigate to the parent object record page and click edit page
2. Drag the RelatedListComponent to the desired space
3. Type in the relevant attributes
4. The related list will show
![Alt text](ReadMeImg/editPage.png?raw=true "Title")
![Alt text](ReadMeImg/dragComponent.png?raw=true "Title")

### Key Attributes
#### 1. Object
This field is used in the SOQL after FROM Clause. This is the API name of your related object, be careful with the letter case, it matters when you try to create a related record. It supports custom objects as well.
##### Example 1: Object B
![image](https://user-images.githubusercontent.com/105597767/168587897-2348020f-55e3-44ca-aa16-df0a9fada641.png)


#### 2. Title
This the title of your realted list.
![image](https://user-images.githubusercontent.com/105597767/168588000-e0f5fafa-ec75-4ba8-9729-7fc57965355a.png)


#### 3. Fields
This field is used in the SOQL after SELECT Clause. Specify all the fields API name that you want to display for the related object. Seperate each field with a semi-column.
##### Example 1: Name
![image](https://user-images.githubusercontent.com/105597767/168588137-8af833bf-aa11-4c46-9535-68ac84795da4.png)


#### 5. Conditions
This field is used in the SOQL after WHERE Clause. You can use this field to filter your related list. Use the variable "recordId" to specify the relationship column (e.g. Object_A_Field__c= : recordId) or otherwise the component will choose from all record.
##### Example 1:
![image](https://user-images.githubusercontent.com/105597767/168588306-da7679af-4f39-416a-8f30-b0b427b26d7c.png)
![image](https://user-images.githubusercontent.com/105597767/168588394-a63e914f-c044-4742-a4a8-577cd6fd9674.png)



#### 7. Limit
This field is used in the SOQL after LIMIT Clause. This will limit the maximum records showing in the related list. The remaining records can be seen by clicking "View More"
##### Example 1:
![image](https://user-images.githubusercontent.com/105597767/168588524-0df5a9ee-3c20-4c4a-a6b2-1c4cf093d2a9.png)


#### 8. ActionList
Choose from create,view and edit to show in the action list of the related record. User semi-column to seperate each action.
##### a. Create
##### b. Edit
##### c. View

#### 10. DisplayFormat
Choose from Tile or List.
##### Example 1: List
![image](https://user-images.githubusercontent.com/105597767/168588561-53bcc4a5-c0f8-4ad2-810e-0ad834bfad60.png)


##### Example 2: Tile
![Uploading image.png…]()

..end/
