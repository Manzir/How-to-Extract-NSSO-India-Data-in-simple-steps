# How-to-Extract-NSSO-India-Data-in-simple-steps by using stata

About NSSO Data 
Nsso data is one of the largest survey data conducted by NSSO in India under the supervision of MOSPI. This survey data covers brad range of issues like Employment, Unemployment, housing condition, domestic tourism, Drinking water, sanitation, Land and livestock holdings, Social consumption, health, Domestic tourism expenditure, Labour Force, Construction, Industries, Manufacture, etc. The data is collected through various rounds depending on the speacfic issue  covered. The data is later dissminated through reports, working papers and other forms to share the different scenerios of the covered issues. The data is also shared with public through raw. files to carry out further research.The data is shared through raw.txt files, which are later extracted and analysed depending on the need. Though the data extraction is an easy process, but most of the times it seems complicated for those who are new to data extraction process. So below i will show you how you can extract data through simple steps. For any help/quiery contact me @ manzirkashmiri@gmail.com
Extraction Methods:
There are multiple methods through wich raw data can be extracted, depending upon you knowledge  and command on statistical tools. You can analyse nsso data through any software like excel  SPSS stata R Python e.t.c. But since most of the research students are comfortable with excel, spss and stata so I will show you how we extract it through using stata, spss and excel. I will show you one of the easiest methods of extraction, but data extraction is not speacific to this method alone in any of these softwares.
Key Points 
To extract data you must have one of the above softwares installed in your PC
Download the data from ICSSR data archive or from the given weblink mospi.nic.in/download-tables-data 
You have to download the raw data files which are in text format along with the layout file
Read the layout file properly which provides the layout formation of the variables covered in through different blocks
Every block represents a set of speacific information collected about the surveyed people
The layout of the data is provided through different levels comprosied of a block or a set of blocks
You must have the same number of raw.txt files and the number of levels in excel.
Extraction in Stata
Step 1  
Preparing a DCT file
*The dct file can be prepaered both in excel, stata and notepad 
To prepare dct in excel
Write command name in first colomun, variable name in second  colomun foled by byte position given in the layout file 
Now write "str" in Command Name "B1&2L01V001" as a variable name (You can your own name), and finally write the byte positions 1-3 in this case. Remember give single space between 1 and 3 seperated by Dash as shown below
Follow the similar steps for all the vaiables in the level 1 of the layout and prepare the level 1 file 
Command Name  Variable Name   Byte Position
 str          B1&2L01V001    1  -  3
 .
 .
 .
 }
 . . . is the number of items
Note: change the byte position and variable name according to the number of items in the the given level
Once you have prepared for all the items 
Once you prepared the level 
Now copy the level 1 prepared in excel and past it in do file follwed by closing brackets or by opening a notpad file 
The level 1 file will look like following 
**infix dictionary
{
str	B1&2L01V001	1	 -	3
str	B1&2L01V002	4	 -	8
str	B1&2L01V003	9	 -	10
str	B1&2L01V004	11	 -	13
str	B1&2L01V005	14	 -	14
str	B1&2L01V006	15	 -	15
str	B1&2L01V007	16	 -	18
str	B1&2L01V008	19	 -	20
str	B1&2L01V009	21	 -	22
str	B1&2L01V010	23	 -	24
str	B1&2L01V011	25	 -	25
str	B1&2L01V012	26	 -	26
str	B1&2L01V013	27	 -	30
str	B1&2L01V014	31	 -	31
str	B1&2L01V015	32	 -	32
str	B1&2L01V016	33	 -	34
str	B1&2L01V017	35	 -	36
str	B1&2L01V018	37	 -	41
str	B1&2L01V019	42	 -	43
str	B1&2L01V020	44	 -	44
str	B1&2L01V021	45	 -	45
str	B1&2L01V022	46	 -	46
str	B1&2L01V023	47	 -	50
str	B1&2L01V024	51	 -	54
str	B1&2L01V025	55	 -	58
str	B1&2L01V026	59	 -	64
str	B1&2L01V027	65	 -	70
str	B1&2L01V028	71	 -	73
str	B1&2L01V029	74	 -	74
str	B1&2L01V030	75	 -	75
str	B1&2L01V031	76	 -	76
str	B1&2L01V032	77	 -	77
str	B1&2L01V033	78	 -	78
str	B1&2L01V034	79	 -	126
str	B1&2L01V035	127	-	129
str	B1&2L01V036	130	-	132
str	B1&2L01V037	133	-	142
}
 Save the file as dct in stata or notepad
 Step 2 
 Use  the fowlling command to extract the final data in stata format 
 infix using "Path of dct file", using ("Path of raw.txt file")
 This is the simplest way to extract nsso data in stata using the two step simple extracting procedure 
 The procedure is explained through pictures as well attached in the repository 
 For any quries or  data processing feel free to contact me at manzirkashmiri@gmail.com
 
