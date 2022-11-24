Project Name: Library Catalogue System

Functions

    1. Login/logout/register
        • Each user account has a userid and password.
        • Upon successful login, userid should be stored in a session

    2. Create new user documents
            user document contain the folling attributs:
                username
                password
            all fields are mandatory

    3. Create new books documents
            books documents contain the following attributes:
                Publisher           
                Author              
                Title               
                Subject             
                PubYear             
                ISBNs               
                HEBID               
                Handle              
                LocationPublished 
        All fields are mandatory which HEBID should be unique


    
    4. Update Book documents
        inventory documents can be updated by Users that logged in

    5. Display inventory documents
        display all documents 

    5. Delete inventory documents
            The document can be deleted by Users that logged in

    6. Provide the following RESTful service
        Request                 Parameters                  Response
        Get login               msg                         html
        Post login              req.body,{User doc}         html
        get /                   req.session                 [{bookdoc1},  
                                item                        doc2}..],html
        get reg                 warning                     html
        post reg                req.body                    html
        get edit                req.params                  html,{book doc}
        post edit               req.body,{book doc}         html
        post logout             {}                          html
        get /create             {}                          html
        post /create            req.body,{book doc}         html
        get del                 req.body`                   html

The server can pass different test cases. Here is a sample stest case
   1 Precondition:
    
    Steps:
    o register as any UserID and any password
    Expected outcome:
    o The System successfully register the new user.

   2 Precondition:
    registered userID and password
    Steps:
    o register as any registered UserID and any password
    Expected outcome:
    o The System block registering the new repeated user.

   3 Precondition:
    
    Steps:
    o login as any userID and any password not registered
    Expected outcome:
    o The System block the unregistered user.


   4 Precondition:
        registered userID and password
    Steps:
    o login as any name and any password registered
    Expected outcome:
    o The System show the index page with userID.

   5 Precondition:
        
    Steps:
    o login as any name and any password not registered
    Expected outcome:
    o The System block the unregistered user.

   6 Precondition:
        
    Steps:
    o login as any name and any password not registered
    Expected outcome:
    o The System block the unregistered user.

   7 Precondition:
        logged in
    Steps:
    o click logout
    Expected outcome:
    o The System return to login page.

 8 Precondition:
        logged in
    Steps:
    o click add new document
        enter reapeted HEBID
        click submit
        go back
        enter some of the fields
        click submit
        go back
        enter all of the fields
        click submit
        go back
    Expected outcome:
    o The System will prevent saving uncompleted inputs and repeated HEBID
    the system will add the new book document if all fields are entered and not repeated HEBID

    9 Precondition:
        logged in
    Steps:
    
        click edit on any record in index page
        enter reapeted HEBID other than own
        click submit
        go back
        enter some of the fields
        click submit
        go back
        enter all of the fields
        click submit
        go back
    Expected outcome:
    o The System will prevent saving uncompleted inputs and repeated HEBID
    the system will update the book document if all fields are entered and not repeated HEBID

 10 Precondition:
        logged in
    Steps:
   
        click delete on any record in index page
        
    Expected outcome:
    The system will show the index page without the deleted record
