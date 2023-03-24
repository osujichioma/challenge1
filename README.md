# challenge1
The objectives of the cleaning exercise was to ensure; 
1. All the columns had a proper and consistent data type.
2. The numerical data columns were fit for calculations and analysis.

ABOUT THE DATASET

The dataset used for the challenge is FIFA 21. It was gotten and can be sourced from kaggle (https://www.kaggle.com/datasets/yagunnersya/fifa-21-messy-raw-dataset-for-cleaning-exploring). The dataset was web scrapped from sofifa.com and presented in a very messy state. The dataset contains details of football players and their performances till 2021. There are 18979 rows and 77 columns present in the FIFA 21 data.

DATA CLEANING PROCESS 

Under the data cleaning phase, some columns had incorrect datatypes, inconsistencies in naming, special characters, null values, empty rows etc.

1. To perform an adequate analysis or EDA process using python, some libaries needed to be imported (Pandas and Numpy) and the FIFA 21 dataset was loaded using the .read_csv funtion. Also, the function .head was used to look at the dataset to figure out how best to start the cleaning process.
![image](https://user-images.githubusercontent.com/100517015/227386542-754621c6-6426-474f-b244-1e10ff0aa489.png)

2. For the analysis, some columns were dropped as they were not so relevant for the analysis and the columns dropped were photoUrl, playerUrl and Loan date end. The Loan date end column [18], had 17,966 missing columns. At this point, the dataset contained 74 columns and 18979 rows.
![image](https://user-images.githubusercontent.com/100517015/227388103-7ca0d60b-027d-4f58-bdad-871df483888a.png)

3. The next step was to check for null values in the dataset and it was discovered that the 'Hits' column had 2595 null values and it was replaced with '0s'. The reason was to ensure that the column was fit for numeric analysis
![image](https://user-images.githubusercontent.com/100517015/227388673-2ce7e79a-f27f-402b-8fb7-9a977c995582.png)

4.The next column cleaned was 'Joined' column. Here, the datatype was presented wrongly and needed to be cleaned. The first step was to import the datetime from the datetime library and using a for loop, the datatype was changed to datetime64
![image](https://user-images.githubusercontent.com/100517015/227389048-1ebebe41-898b-4526-ada8-c951b8be58e6.png)
![image](https://user-images.githubusercontent.com/100517015/227389098-bd840204-5846-496f-9e18-9cb53b88c632.png)
![image](https://user-images.githubusercontent.com/100517015/227389156-be05aec8-af2f-4fc8-952e-8f597e71f9af.png)

5. In data cleaning, it is important to ensure consistency in naming conventions and thus, the column called '↓OVA' was changed to 'OVA'. Also, the 'Clubs' column contained '\n\n\n\n\' and this was replaced with space ''
![image](https://user-images.githubusercontent.com/100517015/227391039-9ed39579-13a3-41f3-a903-552950e189e8.png)

6. The next column cleaned was the 'Contract' renmaned as 'Contractstatus'. The column contained values like '~', 'Dec 31 on loan', 'free'. This was changed to reflect '~' as ACTIVE status, 'free' as FREE status and 'on loan' as ON LOAN status and casted as an 'object64' datatype.
![image](https://user-images.githubusercontent.com/100517015/227396185-d50edd25-e431-4a56-b3b4-66a91535f413.png)
![image](https://user-images.githubusercontent.com/100517015/227396420-02179c4a-9f80-4d0b-901c-6b3309221adf.png)

7. The next column cleaned was the 'Positions' column. The column was reordered by ascending order.
![image](https://user-images.githubusercontent.com/100517015/227400322-27bc172a-ac04-4259-9e83-4e80049f603f.png)

8. The W/F,SM and IR columns have ★ in them and needed to be cleaned. 
![image](https://user-images.githubusercontent.com/100517015/227404456-6945ac5e-f739-4e3e-b13f-699a51ef12c7.png)

9. The 'Height' and 'Weight' column were cleaned as they contained '\' and 'cm' and 'kg' and 'lbs' respectively. The datatype was changed from 'object64' to 'int64'
![image](https://user-images.githubusercontent.com/100517015/227402512-95a47748-905f-4691-af05-cbdaa7add290.png)
![image](https://user-images.githubusercontent.com/100517015/227402536-7c4d15d0-0598-4158-8775-e621310ea75a.png)
![image](https://user-images.githubusercontent.com/100517015/227402855-c8837451-eaf3-4f34-8876-b68746e70a0e.png)

10. The 'Release clause', 'Wage' and 'Value' column was cleaned, the £(sign) was removed, the 'M' sign Was converted to 1,OOO,OOO while the 'K' sign was converted to 1,000 and the data type was changed to 'int64'
![image](https://user-images.githubusercontent.com/100517015/227403000-4201c347-47f8-4514-a4a1-0d0c22cdaf19.png)
![image](https://user-images.githubusercontent.com/100517015/227403130-25095dfb-2585-4ede-a680-89ce744ca30c.png)
![image](https://user-images.githubusercontent.com/100517015/227403183-b8a5169f-c502-4184-8d6f-8ecd89890d44.png)
![image](https://user-images.githubusercontent.com/100517015/227403321-d7981c51-86c9-41d7-8912-5b2bc767d9cc.png)

11. The 'Hits' column contained 'K' and it was converted to 1,000 and set as  a int64 datatype
![image](https://user-images.githubusercontent.com/100517015/227403840-37660cf6-9ab0-49c0-9769-46d303e6b0b8.png)
![image](https://user-images.githubusercontent.com/100517015/227404032-837ee73e-ee6a-4cc0-a5bb-45a3baa8f030.png)
