# FSTA--Software-analysis-and-Design
Project Overview

The FSTA Tour Reservation System is an online web application designed to digitalize and automate the operations of FSTA, a small to medium-sized tour agency. Previously, all booking and tour management were handled physically at the outlet. This system enables efficient handling of core operations, such as:

Creating and approving tour packages

Managing tour groups and their schedules

Customer bookings and payment processing

Assigning and managing tour guides

Enquiring tour costs and guide costs

The system improves operational efficiency, reduces manual errors, and enhances the customer experience through online access.

Key Features
1. Tour Package Management

Create, update, and approve tour packages

Maintain package details including price, cost, itinerary, and deposit

2. Tour Group Management

Create and maintain tour groups linked to approved packages

Update departure dates, status, and remarks

3. Booking Management

Customers and Ops Staff can place bookings

Track booking status: processing, pending, confirmed, or cancelled

Integrates with external payment gateway

Automated scheduler for payment reminders and confirmations

4. Tour Guide Management

Assign tour guides to tour groups

Track availability and calculate costs based on guide type and rank

Enter tour completion remarks

5. Enquiry Functions

Enquire tour packages, tour costs, and tour guide costs

Search bookings by customer, tour group, or tour package

6. Notifications

Email alerts for booking confirmations, cancellations, and payment updates

System Actors
Actor	Description
Customer	Browse and book tour packages, make payments, and receive email notifications
Ops Staff	Manage tours, bookings, staff assignments, and customer requests
Ops Manager	Approve tour packages and oversee operations
Tour Guide	Lead tours and provide remarks on completed tours
Payment System	Handles external payment processing
Daily Scheduler	Automated process for outstanding payments and notifications
Email System	Sends booking and payment notifications
Data Model

The system uses a relational data model with key entities:

Staff: StaffID, Name, Email, Phone, Role

Customer: CustomerID, Name, Email, Phone, Address, CreditCardDetails

TourPackage: PackageID, Name, Description, Price, Cost, Deposit, Country, NumOfDays, Itinerary, ApprovalStatus

TourGroup: GroupID, PackageID, Status, Pax limits, DepartureDate, MeetingPlace, Remarks

Booking: BookingID, CustomerID, StaffID, TourGroupID, BookingStatus, PaymentMethod, TotalPrice, BookingDate

TourGuide: TourGuideID, Name, GuideType, Rank, Rate, Contact Info

TourGuide-TourGroup: Assignment table linking guides to groups

Use Cases

The system supports 14 main use cases:

Create Tour Package

Approve Tour Package

Create Tour Group

Enquire Tour Package

Place Booking

Enquire Booking

Confirm Booking

Cancel Booking

Cancel Tour Group

Update Tour Group Departure

Enquire Tour Guide Cost

Complete Tour

Enquire Tour Cost

Assign Tour Guide

Each use case includes forms, control classes, and entity interactions, with validation, error handling, and status updates.

Design Highlights
Object-Oriented Design

Polymorphism is used for the TourGuide class:

Abstract class TourGuide defines common attributes and the abstract calculateCost() method.

Subclasses PartTimeTourGuide and FullTimeTourGuide implement calculateCost() differently based on guide type and rank.

Ensures cohesive, reusable, and loosely coupled design.

Sequence & Class Diagrams

Each use case is supported by UML diagrams detailing actor interactions, control logic, and entity operations.

Technical Notes

Bookings are created as “processing”, updated to “pending” after deposit, and “confirmed” after full payment.

Refunds and account creation are reserved for future enhancements.

Payment is handled externally and is not part of the system core.

Email notifications are integrated for customer and staff updates.


