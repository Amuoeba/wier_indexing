# wier_indexing
## Project description
In this project we implemented an inverted index and query system against it for a set of 1416 localy stored websites. 
Goal of the project was also to analize performance difference between querying an inverted index and searching the documents
incrementaly. For this reason we also implemented a simple incremental query search algorithm.

## Dependancies needed to set up the project
* python 3.6
* pandas 1.0.3
* beautifulsoup4            4.8.2
* nltk                      3.4.5  With punkt tokenizer models and stopword corpora installed
* sqlite                    3.31.1

## How to run the project
1. clone the repository in an empty directory
2. run `cd implementation_indexing/` to make  `implementation_indexing/` your working directory
3. Project can be run in two modes:
      * Search with inverted index:
          * run `python run_sqlite_seqrch.py "word1 word2 ..."` where  `"word1 word2 ..."` is a parameter with any number
          wods you wish to querry against. This parameter must be present and should contain at least one word
      * Search with basic incremental search:
          * run `python run_basic_search.py "word1 word2 ..."` where  `"word1 word2 ..."` is a parameter with any number
          wods you wish to querry against. This parameter must be present and should contain at least one word

## Example results
### Inverted index search
Query string: šola
```
python run_sqlite_seqrch.py "šola"
Querring for:['šola']
Found 7 documents in 0.0015423297882080078s
Frequency      Document name                                     Snipet 0                                                    Snipet 1                                                    Snipet 2                                                    Snipet 3                                                    Snipet 4                                                    
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
582            podatki.gov.si/podatki.gov.si.340.html            .... OSNOVNA ŠOLA SLOVENSKA BISTRICA...                     ...Tržič BIOTEHNIŠKA ŠOLA MARIBOR BIOTEHNIŠKA...            ...MARIBOR BIOTEHNIŠKA ŠOLA RAKIČAN BIOTEHNIŠKI...          ...- Zasebna šola za varnostno...                           ...DRUGA OSNOVNA ŠOLA SLOVENJ GRADEC...                     
10             evem.gov.si/evem.gov.si.371.html                  ...Waldorfska osnovna šola ) ·...                           ...in zasebne šola morajo imeti...                          ...in zasebne šola morajo imeti...                          ...delodajalcev . Šola mora imeti...                        ...izobrazbo . Šola mora poleg...                           
3              e-uprava.gov.si/e-uprava.gov.si.16.html           ...... Osnovna šola Kdaj in...                              ...... Srednja šola Kdaj lahko...                           ...in višja šola Kakšni so...                               
1              evem.gov.si/evem.gov.si.535.html                  ...in pomorska šola Piran O...                              
1              evem.gov.si/evem.gov.si.650.html                  ...Gorsko vodništvo Šola vožnje Izvajanje...                
1              evem.gov.si/evem.gov.si.651.html                  ...tolmačenje Š Šola vožnje Specializirano...               
1              evem.gov.si/evem.gov.si.654.html                  ...Gorsko vodništvo Šola vožnje Izvajanje...                
Snippets found in: 5.439236402511597s

```

### Basic incremental search
Query string: šola
```
python run_basic_search.py "šola"
Querring for:['šola']

Processing document 1416/1416
Found 7 documents in: 53.15174198150635
Frequency      Document name                                     Snipet 0                                                    Snipet 1                                                    Snipet 2                                                    Snipet 3                                                    Snipet 4                                                    
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
582            podatki.gov.si/podatki.gov.si.340.html            .... OSNOVNA ŠOLA SLOVENSKA BISTRICA...                     ...Tržič BIOTEHNIŠKA ŠOLA MARIBOR BIOTEHNIŠKA...            ...MARIBOR BIOTEHNIŠKA ŠOLA RAKIČAN BIOTEHNIŠKI...          ...- Zasebna šola za varnostno...                           ...DRUGA OSNOVNA ŠOLA SLOVENJ GRADEC...                     
10             evem.gov.si/evem.gov.si.371.html                  ...Waldorfska osnovna šola ) ·...                           ...in zasebne šola morajo imeti...                          ...in zasebne šola morajo imeti...                          ...delodajalcev . Šola mora imeti...                        ...izobrazbo . Šola mora poleg...                           
3              e-uprava.gov.si/e-uprava.gov.si.16.html           ...... Osnovna šola Kdaj in...                              ...... Srednja šola Kdaj lahko...                           ...in višja šola Kakšni so...                               
1              evem.gov.si/evem.gov.si.650.html                  ...Gorsko vodništvo Šola vožnje Izvajanje...                
1              evem.gov.si/evem.gov.si.654.html                  ...Gorsko vodništvo Šola vožnje Izvajanje...                
1              evem.gov.si/evem.gov.si.535.html                  ...in pomorska šola Piran O...                              
1              evem.gov.si/evem.gov.si.651.html                  ...tolmačenje Š Šola vožnje Specializirano...  

```

