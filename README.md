# DenverRealEstate2013



http://data.opencolorado.org/dataset/city-and-county-of-denver-real-property-sales-book-2013/resource/b4d6ebbe-ead8-47dd-91f6-a8edc8cbaa87		
	review in google sheets	
		
	Upload to sql	
		
		
Start w/ sales book		
	load all data into google sheets, review	
		
	load data into SQL	
		
	create subset w/ interesting columns	
		
	To account for location, picked 10 parcel areas, with similar area and housing	
  
  create view [dbo].[sales_book_2013_10Parcel_SDenver] as 
SELECT    NBHD,    LIVEAREA, FINBSMNT, BASEMENT, YRBUILT, CONDITION, QUALITY, STORIES, NUMBDRM, NUMBATHS, GARTYPE, ARCSTYLE, SPRICE, NETPRICE
FROM            dbo.SalesBook_2013
WHERE        (LIVEAREA <> '') AND (FINBSMNT <> '') AND (BASEMENT <> '') AND (YRBUILT <> '') AND (CONDITION <> '') AND (QUALITY <> '') AND (STORIES <> '') AND (NUMBDRM <> '') AND (GARTYPE <> '') AND (ARCSTYLE <> '') AND 
                         (SPRICE <> '') AND (NETPRICE <> '')
						 AND LEFT(Parcel,5) in ('07044','07046', '07092','07042','07061','07052','06314','07091','07051','07054')
		
	removed a bunch of columns	
