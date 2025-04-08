# Cycle Time Efficiency Calculations

## Overview
This document provides calculations for the cycle time efficiency of both EverSure's traditional and digital processes. Cycle time efficiency is calculated as the ratio of value-added time (processing time) to the total cycle time (processing time + waiting time).

Formula: Cycle Time Efficiency = Processing Time / (Processing Time + Waiting Time)

## Assumptions
- Working week of 40 hours as specified in the project requirements
- All times are converted to hours for consistency
- Sequential process flow (no parallel activities)
- For activities without specified waiting times, waiting time is assumed to be 0
- For activities with specified total time but unspecified processing time, reasonable estimates are made

## Traditional Process Calculations

### 1. Initial Customer Identification
- Processing Time: 2 hours
- Waiting Time: 0 hours
- Subtotal: 2 hours processing, 0 hours waiting

### 2. Customer Report Preparation
- Processing Time: 4 hours
- Waiting Time: 1 week = 40 hours
- Subtotal: 4 hours processing, 40 hours waiting

### 3. Client Meeting (Booking, Preparation, Meeting)
- Processing Time: 3 hours
- Waiting Time: 2 weeks - 3 hours = 77 hours
- Subtotal: 3 hours processing, 77 hours waiting

### 4. Offer Preparation (for interested clients)
- Processing Time: 4 hours (sales admin) + 1 hour (sales) = 5 hours
- Waiting Time: 3 days - 5 hours = 19 hours (assuming 8-hour workdays)
- Subtotal: 5 hours processing, 19 hours waiting

### 5. Offer Response
- Processing Time: 0 hours (customer activity)
- Waiting Time: 2 weeks = 80 hours
- Subtotal: 0 hours processing, 80 hours waiting

### 6. Contract Processing
- Processing Time: 3 hours
- Waiting Time: 0 hours
- Subtotal: 3 hours processing, 0 hours waiting

### 7. Payment Processing (Normal Case - 95%)
- Processing Time: 4 hours
- Waiting Time: 0 hours
- Subtotal: 4 hours processing, 0 hours waiting

### 8. Payment Processing (Error Case - 5%)
- Processing Time: 4 hours + 1 hour = 5 hours
- Waiting Time: 2 days = 16 hours
- Subtotal: 5 hours processing, 16 hours waiting

### Total Traditional Process (Normal Path, No Modifications, No Payment Errors)
- Total Processing Time: 2 + 4 + 3 + 5 + 0 + 3 + 4 = 21 hours
- Total Waiting Time: 0 + 40 + 77 + 19 + 80 + 0 + 0 = 216 hours
- Total Cycle Time: 21 + 216 = 237 hours
- Cycle Time Efficiency: 21 / 237 = 0.0886 or 8.86%

### Total Traditional Process (With Offer Modifications and Payment Errors)
- Additional Processing Time for Modifications: Estimated 2 hours
- Additional Waiting Time for Modifications: 2 weeks = 80 hours
- Total Processing Time: 21 + 2 + (5-4) = 24 hours
- Total Waiting Time: 216 + 80 + 16 = 312 hours
- Total Cycle Time: 24 + 312 = 336 hours
- Cycle Time Efficiency: 24 / 336 = 0.0714 or 7.14%

## Digital Process Calculations

### 1. Lead Generation
- Processing Time: 6 hours
- Waiting Time: 0 hours
- Subtotal: 6 hours processing, 0 hours waiting

### 2. Lead Processing (Algorithm)
- Processing Time: Estimated 0.1 hours (automated)
- Waiting Time: 0 hours
- Subtotal: 0.1 hours processing, 0 hours waiting

### 3. Offer Preparation
- Processing Time: 10 minutes = 0.17 hours
- Waiting Time: 0 hours
- Subtotal: 0.17 hours processing, 0 hours waiting

### 4. Offer Response
- Processing Time: 0 hours (customer activity)
- Waiting Time: 3 weeks = 120 hours
- Subtotal: 0 hours processing, 120 hours waiting

### 5. Accepted Offer Processing
- Processing Time: 3 hours
- Waiting Time: 4 days = 32 hours
- Subtotal: 3 hours processing, 32 hours waiting

### 6. Data Entry into AUIN (Normal Case - 85%)
- Processing Time: Estimated 1 hour
- Waiting Time: 0 hours
- Subtotal: 1 hour processing, 0 hours waiting

### 7. Data Entry into AUIN (Error Case - 15%)
- Processing Time: Estimated 2 hours
- Waiting Time: Estimated 8 hours
- Subtotal: 2 hours processing, 8 hours waiting

### 8. Contact Request Handling (Alternative Path)
- Processing Time: 4 hours
- Waiting Time: 2 days = 16 hours
- Subtotal: 4 hours processing, 16 hours waiting

### Total Digital Process (Normal Path, Direct Acceptance)
- Total Processing Time: 6 + 0.1 + 0.17 + 0 + 3 + 1 = 10.27 hours
- Total Waiting Time: 0 + 0 + 0 + 120 + 32 + 0 = 152 hours
- Total Cycle Time: 10.27 + 152 = 162.27 hours
- Cycle Time Efficiency: 10.27 / 162.27 = 0.0633 or 6.33%

### Total Digital Process (With Contact Request)
- Total Processing Time: 6 + 0.1 + 0.17 + 0 + 4 + 3 + 1 = 14.27 hours
- Total Waiting Time: 0 + 0 + 0 + 120 + 16 + 32 + 0 = 168 hours
- Total Cycle Time: 14.27 + 168 = 182.27 hours
- Cycle Time Efficiency: 14.27 / 182.27 = 0.0783 or 7.83%

### Total Digital Process (With Errors)
- Total Processing Time: 6 + 0.1 + 0.17 + 0 + 3 + 2 = 11.27 hours
- Total Waiting Time: 0 + 0 + 0 + 120 + 32 + 8 = 160 hours
- Total Cycle Time: 11.27 + 160 = 171.27 hours
- Cycle Time Efficiency: 11.27 / 171.27 = 0.0658 or 6.58%

## Summary of Cycle Time Efficiency

### Traditional Process
- Best Case (No Modifications, No Errors): 8.86%
- Worst Case (With Modifications and Errors): 7.14%
- Average Case (Weighted by probabilities): ~8.5%

### Digital Process
- Best Case (Direct Acceptance, No Errors): 6.33%
- With Contact Request: 7.83%
- With Errors: 6.58%
- Average Case (Weighted by probabilities): ~6.5%

## Observations
1. Both processes have low cycle time efficiency (under 10%), indicating significant waiting time compared to processing time.
2. The traditional process has slightly higher cycle time efficiency than the digital process in the best case scenario.
3. The digital process has shorter overall cycle time (162-182 hours vs. 237-336 hours for traditional).
4. The traditional process has more processing time (21-24 hours vs. 10-14 hours for digital).
5. Waiting times dominate both processes, with the traditional process having more waiting time overall.

## Improvement Opportunities
1. Reduce waiting time for customer report preparation in the traditional process
2. Reduce waiting time between report receipt and client meeting in the traditional process
3. Reduce customer response waiting time in both processes
4. Improve data verification process to reduce waiting time in the digital process
5. Reduce error rates in both processes to avoid additional processing and waiting time
