# CST8915 Lab 1: Algonquin Pet Store on Azure VM

**Student Name**: Jack Loder
**Student ID**: 040829366
**Course**: CST8915 Full-stack Cloud-native Development
**Semester**: Fall 2026

---

## Demo Video

🎥 [Watch Demo Video](https://youtu.be/NvGHapt6lmI)

---

## Technical Explanations

### Order Service (Node.js)

The Order Service is responsible for accepting customer orders from the storefront and sending them to RabbitMQ for processing. When a shopper selects a product and enters a quantity, the storefront sends the order details to this service on port 3000, where it validates the request and publishes the message into the order queue, relaying them to RabbitMQ. Node.js is used here because it is well-suited to handling lightweight HTTP APIs and event-driven workloads

### Product Service (Rust)

The Product Service is responsible for serving the product catalog that the storefront uses to display available items and calculate order totals. It exposes product information through a REST API, allowing the front-end to fetch product data independently of the ordering process. Rust is used because of it's high performance, memory safety, and reliability, which makes it great for an API that serves data quickly and predictably. In the system, this service communicates with the storefront over HTTP

### Store Front (Vue.js)

The Store Front is the customer-facing web application that allows users to browse products. It loads product data from the Product Service, renders the homepage with available produts, and collects the user’s order via a form before sending it to the Order Service. This makes it the main user interaction layer in the architecture. Vue.js is used because it is a modern framework for building interactive user interfaces, great for building a simple site liek this. In the microservices architecture, the Store Front communicates with the Product Service to retrieve catalog data and with the Order Service to submit orders.

## Acknowledgments

[Vue.js FAQ](https://vuejs.org/about/faq.html)

My rust dev girlfriend

copilot used for research and spell check and grammar pass.