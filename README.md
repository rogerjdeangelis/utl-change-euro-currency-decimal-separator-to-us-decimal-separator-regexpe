# utl-change-euro-currency-decimal-separator-to-us-decimal-separator-regexpe
Change euro currency decimal separator to us decimal separator
    Change euro currency decimal separator to us decimal separator                                                               
                                                                                                                                 
    In most European countries, a comma is used to separate the                                                                  
    integral part of a number from the decimal part.                                                                             
                                                                                                                                 
    300,00 is 300 Euros and 10 cents                                                                                             
                                                                                                                                 
    I need to change 300,00 to 300.00 using an informat                                                                          
                                                                                                                                 
    github                                                                                                                       
    https://tinyurl.com/y8lgqbfv                                                                                                 
    https://github.com/rogerjdeangelis/utl-change-euro-currency-decimal-separator-to-us-decimal-separator-regexpe                
                                                                                                                                 
    SAS Doc                                                                                                                      
    https://tinyurl.com/y8uvj49r                                                                                                 
    https://documentation.sas.com/?docsetId=proc&docsetTarget=n1jriq5xib5j45n1pwpwzk311v0p.htm&docsetVersion=9.4&locale=en       
                                                                                                                                 
     _                   _                                                                                                       
    (_)_ __  _ __  _   _| |_                                                                                                     
    | | `_ \| `_ \| | | | __|                                                                                                    
    | | | | | |_) | |_| | |_                                                                                                     
    |_|_| |_| .__/ \__,_|\__|                                                                                                    
            |_|                                                                                                                  
    123,88                                                                                                                       
    287,52                                                                                                                       
    111,12                                                                                                                       
                 _               _                                                                                               
      ___  _   _| |_ _ __  _   _| |_                                                                                             
     / _ \| | | | __| `_ \| | | | __|                                                                                            
    | (_) | |_| | |_| |_) | |_| | |_                                                                                             
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                            
                    |_|                                                                                                          
    123.88                                                                                                                       
    287.52                                                                                                                       
    111.12                                                                                                                       
                                                                                                                                 
     _ __  _ __ ___   ___ ___  ___ ___                                                                                           
    | `_ \| `__/ _ \ / __/ _ \/ __/ __|                                                                                          
    | |_) | | | (_) | (_|  __/\__ \__ \                                                                                          
    | .__/|_|  \___/ \___\___||___/___/                                                                                          
    |_|                                                                                                                          
                                                                                                                                 
                                                                                                                                 
    proc format;                                                                                                                 
       invalue $euro_to_us (default=7)                                                                                           
         's/\,/./' (regexpe) = _same_                                                                                            
       other=_error_;                                                                                                            
    run;quit;                                                                                                                    
                                                                                                                                 
                                                                                                                                 
    data want;                                                                                                                   
       input currency:$euro_to_us6.;                                                                                             
       put currency=;                                                                                                            
    cards4;                                                                                                                      
    123,88                                                                                                                       
    287,52                                                                                                                       
    111,12                                                                                                                       
    ;;;;                                                                                                                         
    run;quit;                                                                                                                    
                                                                                                                                 
    Up to 40 obs from WANT total obs=3                                                                                           
                                                                                                                                 
    Obs    currency                                                                                                              
                                                                                                                                 
     1      123.88                                                                                                               
     2      287.52                                                                                                               
     3      111.12                                                                                                               
                                                                                                                                 
                                                                                                                                 
                                                                                                                                 
