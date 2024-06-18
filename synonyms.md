 Lines starting with pound are comments and blank lines are ignored.

# Synonym relationships can be defined as unidirectional or bidirectional relationships.

# Unidirection relationships are represented by any term sequence 
# on the left hand side (LHS) of "=>" followed by synonyms on the right hand side (RHS)
CodeStar => AWS CodeStar
# This will map CodeStar to AWS CodeStar, but not vice-versa

# Multiple synonym relationships may be defined in one line as well by comma seperation.
autoscaling group, ASG => Auto Scaling group, autoscaling
# The above is equivalent to:
autoscaling group => Auto Scaling group, autoscaling
ASG => Auto Scaling group, autoscaling

# Bi-directional synonyms are comma separated terms with no "=>"
DNS, Route53, Route 53
# DNS, Route53, and Route 53 map to one another and are interchangeable at match time.
# The above is equivalent to:
DNS => Route53, Route 53
Route53 => DNS, Route 53
Route 53 => DNS, Route53

# Overlapping LHS terms will be merged
Beta => Alpha
Beta => Gamma
Beta, Delta
# is equivalent to:
Beta => Alpha, Gamma, Delta
Delta => Beta

# Synonym rule count is the total number of lines defining synonym relationships.
# Term count is the total number of unique terms for all rules. 
aws => amazon web services
DynamoDb, DDB
SHIPHATS, SHIP-HATS
SGTS, Singapore Government Tech Stack
CStack,Container Stack
CICD, CI/CD
Continuous Integration (CI), CI/CD
Continuous Delivery (CD),Continuous Deployment
Infrastructure as Code (IaC), Programmable Infrastructure
Orchestration, Automation
Deployment Pipeline, Release Pipeline, Delivery Pipeline
Monitoring and Observability,Application Performance Monitoring (APM)
Version Control, Source Control
Agile Development, Agile Software Development
training, learning
FOD, Fortify on demand
# The above has a Synonym rule count of 2 and a Term count of 4. 
# Comments and blanks lines do not count.

