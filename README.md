# assignment-12

# Install storybook
Clone the template: <br>
npx degit chromaui/intro-storybook-react-template taskbox <br>

cd taskbox <br>

Install dependencies: <br>
yarn <br>

# create components
create component folder <br>
write .tsx documents to create components <br>
write .stories.tsx documents to create the content and behaviors of the components <br>
write .css documents to create the styles of the components <br>

# write docker file
# Use the official Node.js image as the base image
FROM node:18

# Set the working directory inside the container
WORKDIR /bao_yuwei_ui_garden

# Copy the package.json and yarn.lock files
COPY package.json yarn.lock ./

# Install the project dependencies
RUN yarn install

# Copy the rest of the project files into the container
COPY . /bao_yuwei_ui_garden

# Builds Storybook application using the build-storybook script from the package.json file.
RUN yarn build-storybook

# Expose the port:8083 the app will run on 
EXPOSE 8083

# Command to run the app on 8083
CMD ["yarn", "storybook", "--port", "8083"]

# resolve the problem that storybook tries to use a linux function which is incompatible with windows browsers
ENV CI=true

# build image
build image on docker 

# solve compatibility problems
change the yarn version in package.json to 1.22.22 to match the global version <br>
delete current image <br>
rebuild image <br>

# build container
build the container with name: bao_yuwei_coding_assignment12 using the previously created image on port 8083 

# run container
run container successfully on port 8083





