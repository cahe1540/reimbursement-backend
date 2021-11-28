# Reimbursement System Flask Server

# prerequisites:
- create a PostgreSQL database (on the cloud, locally,... etc)
- create table worker, and reimbursements
    - use the entities in this project for table schemas
    
# to run: 
- install Python 3.7+ and pip
- cd into directory where this project is located
- create venv with : python3 -m venv venv  
- run command: source ./venv/bin/activate
- run command: pip install -r requirements.txt
- set up environment variables for psychopg2 connection
    -  this can be found in /utils/connection 
- run app with: python main.py


# Routes
#### METHOD: GET
##### /users/login?user_name=<username>&password=<password>
- query params: username, password
- description: endpoint to log in request user info
- returns data for user
  
#### METHOD: GET
##### /employees
- returns: returns a list of all employees

#### METHOD: GET
##### /employees/<employee_id>/reimbursements
- returns: search an employee by id

#### METHOD: GET
##### /reimbursements
- returns: all reimbursements

#### METHOD: POST
##### /reimbursements
- body: reimbursement
- description: endpoint to create a reimbursement
- returns: newly created reimbursement

#### METHOD: PATCH
##### /managers/<manager_id>/reimbursements/<reimbursement_id>
- path params: manager_id, reimbursement_id
- body: changes = {status: <approve/deny>, message: <message>}
- description: endpoint for manager to accept or deny a reimbursement
- returns: newly updated reimbursement

#### METHOD: DELETE
##### /employees/<employee_id>/reimbursements/<reimbursement_id>
- path params: employee_id, reimbursement_id
- description: endpoint for employee to delete own reimbursements if not yet approved or denied
- returns: deleted reimbursement (should be no content in future work)

