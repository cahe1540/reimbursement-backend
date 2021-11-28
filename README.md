# Reimbursement System Flask Server

# to run: 
- install Python 3.7+ and pip
- install virtaulenv with pip install venv
- run command: source ./venv/bin/activate
- run command: pip install -r requirements
- run app with python main.py

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

