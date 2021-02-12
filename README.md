# SRE - Thoughts, Best Practices & Frameworks
 
Due to my background in automation at large scale, I'm often asked for advice on SRE practices.  Fortunately I worked with some of the best SRE's in the business, including https://github.com/nathenharvey - Developer Advocate for Google Cloud Platform.  
  
  
### Question 
When I meet a customer or collegue who askes about SRE, I always ask these initial questions:  
- How did you find out about your last outage ?  
- What was the impact to your customers ?  
- How did your organisation respond ?  
  
### What is SRE
++++++++++
Site Reliability Engineering (SRE) is a set of principles, practices, and organisational constructs that seek to balance the reliability of a service with the need to continually deliver new features.  

The REAL definition.  
Yes, it was created by Google.  SRE is what you get when you treat operations as a software problem.  Using code for availability, latency, performance and capacity.  
  
Some things to remember:  
1. The MOST important feature of any system is it’s reliability.  
2. Our monitoring does not only decide our reliability because our Users do.  
3. Reliability comes for great engineered Software, Operations and Business.  
  
### SRE Measures
The 3 most important measures for an SRE.  

##### SLI - Service Level Indicator
Metrics that describe users experience.  
- Net Promoter Score  
- Twitter sentiment  
- Reddit issues  
  
##### SLO - Service Level Objective
- Our target health - how good does our customer need ?  

##### SLA - Service Level Agreement
- Contractable obligation. 
  
When do we need to make a system more reliable ?

### SRE Framework - Error Budget
What is an `Error Budget` ???   
- Targeting less than 100% reliability means targeting more than 0% unreliability
- An acceptable rate or errors
- This is a budget that can be allocated
  
```bash
Eg.
SLO: 99.9%
Error budget: 100% - 99.9% = 0.1%
For a 1B query/month service - 1 million errors to “Spend” !
```
  
### Implications of Error Budget (behaviours and rules)
What to do when you have budget to spend and what to do when your out of budget !  
  
##### Prioritise Reliability  (when budget is exhausted)
- prioritise postmortem items
- Automate deployment pipelines
- Improve monitoring and observability
- Require SRE consultation
  
##### Prioritise Velocity (When budget is available)
- Expected system changes
- Inevitable failure in hardware, networks, etc
- Planned downtime
- Risky experiments
  
### Site Reliability Hierarchy - Monitoring 
This is the hierachy of SRE's as defined by Google.  
https://www.zenoss.com/blog/dickersons-hierarchy-of-service-reliability
  
### Remember this about incidents
Firefighters say `We have never responded to an emergency` !  They practice to put out a fire on a burning house.  
SRE’s must practice to respond to incidents because outages WILL happen !  
  
As they say:  
```bash
An incident is an unplanned investment !
```
  
### How do we learn from Incidents ?  
The `Framework` is as follows:  
```bash
Detect -> Investigate -> Mitigate -> Fix -> Learn
```

### Resources
- Free books - landing.google.com/sre/books 
- Splunk SRE site - https://www.observability.splunk.com/en_us/infrastructure-monitoring/guide-to-sre-and-the-four-golden-signals-of-monitoring.html


### Going Back to the Questions Above
So, what are the answers to my questions above ?  
  
- How did you find out about your last outage ?
It’s your SLI. 
  
- What was the impact to your customers ?  
It’s your SLO. 
  
- How did your organisation respond ?  
Error budget consequences. 
