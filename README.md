# Midterm assignment for VDT Cloud 2024

## I. Develop a simple 3-tier web application

### Requirements:

-   #### Develop a web application with the following features :
    -   Display a list of students in VDT2024 in a table with the following information: Full name, Gender, and School they are attending.

    - Allow viewing details, adding, deleting, and updating student information.

- ### Design web application:
    - Web Interface: **ReactJs** - Create flexible and responsive user interfaces.
    - API: **FastAPI** - Develop high-performance, easy-to-build and integrate RESTful APIs.
    - Database: **MongoDB** - Flexible NoSQL database, scalable and capable of handling large volumes of data.
    - **Web application architecture**:
    <img src= images/3tier-architecture.png>

- ### Output :
    - vdt2024-web source code
    - vdt2024-api source code
    - unit-test source code
    - Demo web application:
        - List of VDT2024 Cloud students:
        <img src= images/list-students.png>
        - Detele student from the list:
        <img src= images/delete-students.png>
        - Add student to the list:
         <img src= images/add-student.png>
         <img src= images/add-sucessfully.png>
        - Modify student infomation:
        <img src= images/modify-student.png>


## II. Triển khai web application sử dụng các DevOps tools & practices

### 1. Containerization

Requirements:

-   Write a Dockerfile for each repository to package the services into container images.
-   The image should ensure optimized build time and minimal disk space usage, utilizing recommended image building techniques (layer-caching, optimized RUN instructions, multi-stage build, etc.)

Output:

-   File Dockerfile cho từng dịch vụ kế hệ thống với ba dịch vụ:
    -   api : Here is Dockerfile with optimized techniques used:
      ```
      # Use Python 3.9 slim base image for a lightweight starting point
      FROM python:3.9-slim AS builder

      WORKDIR /code

      # Copy the entire application code into the container's working directory
      COPY . /code

      # Use --no-cache-dir to avoid caching downloaded packages, reducing image size
      RUN pip install --no-cache-dir --upgrade -r requirements.txt

      CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "80"]
      ```
    -   frontend : [react]
    -   docker-compose : [docker-compose.yml]

-   Output câu lệnh build và thông tin docker history của từng image:


### 2. Continuous Integration

Yêu cầu:

-   Tự động chạy unit test khi tạo PR vào branch main
-   Tự động chạy unit test khi push commit lên một branch
    Output:
-   File setup công cụ CI
    -   source : [ci file]
-   Output log của luồng CI
    <img src= images/actions.png>

-   Các hình ảnh demo khác
    


### 3. Automation


### 4. Research topic : Who are you, platform engineering
