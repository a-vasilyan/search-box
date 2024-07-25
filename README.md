# search-box


The project is located on the master branch.





MainInput Component

    The MainInput component provides a user interface element for inputting search queries and dynamically 
    filtering data within a web application. It integrates seamlessly with other components to enhance user 
    interaction and search functionality.
    
  Features:
    Dynamic Input Binding: Allows users to input search queries (inputValue) which dynamically updates the 
    displayed results based on user input.
    
    Category and Data Interaction: Receives and displays data (filteredData) from an external API 
    (https://frontend-test-api.digitalcreative.cn/) through parent component interaction.
    
    Event Emission: Emits update-filtered-data event to notify parent components of changes in filtered data, 
    facilitating seamless updates and interaction between components.
    
    Usage:
    Integrate the MainInput component within your Vue.js application to enable enhanced search functionality 
    and user interaction. Ensure proper handling of data bindings and event emissions to maintain 
    synchronized state management across your application.

    
Certainly! Here's a description you can use for the ResultItem component in your readme.md file:






ResultItem Component

The ResultItem component is designed to display individual search results within a list or grid layout in a Vue.js application. It provides structured presentation of data including title, description, and an associated image.

Features:
  Dynamic Content Rendering: Displays dynamic content such as title and description passed as props from 
  parent components.

Image Display: Renders an image (image prop) associated with each result item, facilitating visual 
  representation of search results.

Styling and Interaction:
   Hover Effects: Applies hover effects to enhance user interaction, altering background color and 
  adjusting the visibility of an additional icon (Vector.svg).

Usage:
 Integrate the ResultItem component within your Vue.js application to effectively display and present s 
 earch results or other structured data. Customize styling and behavior as needed to align with your 
  application's design and functionality requirements.


Certainly! Here's a description you can use for the TagButton component in your readme.md file:






TagButton Component

 The TagButton component represents a clickable tag element with optional activation state and dynamic 
 content display in a Vue.js application. It enhances user interaction by allowing selection and filtering 
 based on specified categories or tags.

Features:
 Dynamic Text Content: Displays tagText passed as a prop, allowing for flexible labeling of different 
 categories or tags.

 Click Event Handling: Executes a specified onClick function when clicked, enabling interaction with 
 parent components or triggering actions based on tag selection.

Styling and Interaction:
 Interactive Design: Utilizes hover effects to indicate interactivity (cursor: pointer and background 
 color change).

Visual Feedback: Provides visual feedback through color changes and icon inversion (filter: brightness(0) 
 invert(1)) when active, enhancing usability and user experience.

Usage:
 Integrate the TagButton component within your Vue.js application to facilitate user-driven actions such 
 as filtering content by categories or tags. Customize styling and behavior as needed to align with your 
 application's design and functionality requirements.





  Footer-block Component

  The Footer-block component is designed to display informative messages and statuses related to search 
  results within a Vue.js application's user interface.

Features:
  Dynamic Content: Displays various messages based on application state:

  "searching..." when loading data.
 "{count} results" when search results are available.
  "No result" when no search results are found.
  Custom error message ("Something wrong happened but this is not your fault :)") for error scenarios.
  Responsive Design: Utilizes flexbox (display: flex) for adaptive layout and alignment of content within 
  the footer section.

 Styling: Implements distinct typography styles (font-family, font-size, font-weight, line-height, and 
 color) using the Poppins font to ensure consistent readability and visual appeal.

 Error Handling: Highlights error messages in a distinctive color (#ED2E7E) to differentiate them from 
standard informational messages.

Usage:
 Integrate the Footer-block component at the bottom of your application's user interface to provide clear 
 feedback and status updates related to search operations. Customize the component's appearance and 
 messaging logic to align with specific application requirements and user experience goals.


MainContainer Component

 The MainContainer component serves as a central layout container in a Vue.js application, providing a structured arrangement for displaying content and components.

Features:
Structured Layout: Utilizes flexbox (display: flex) for responsive and organized content placement within the viewport.

Background Styling: Sets a soothing background color (#EDF2F7) to enhance visual appeal and readability of displayed content.

Component Integration: Includes the MainBlock component to encapsulate and manage main application features or content blocks efficiently.

Visual Elements: Incorporates an image (dc) positioned absolutely to the bottom-right corner, adding a decorative or branding element to the layout.

Usage:
Integrate the MainContainer component as the main wrapper for your Vue.js application's content, ensuring consistent layout and visual presentation across different views or pages. Customize styles and content placement within the container to suit specific design requirements and user experience goals.

MainBlock Component

The MainBlock component serves as the central interface for conducting and managing search operations within a Vue.js application.

Features:
Search Input: Includes a MainInput component that allows users to input search queries.

Displays the number of search results (count) dynamically.
Filters data based on selected categories through TagButton components.
Category Filtering: Utilizes TagButton components to filter search results by predefined categories such as "Languages," "Build," "Design," and "Cloud."

Visual Feedback: Provides visual cues and status updates:

Shows a searching animation (searchingImage) when loading data.
Displays an error image (errorImage) when no results are found after a search attempt.
Dynamic Content: Renders ResultItem components dynamically based on filtered search data.

Each ResultItem displays relevant information such as title, description, and an associated image.
Loading Indicator: Features a loading animation (Loader.png) within main-loader-block to indicate active data retrieval processes.

Styling:
Responsive Design: Adapts seamlessly to different screen sizes with a fixed width (650px) and a maximum height (651px).
Scrollbar Customization: Customizes scrollbar appearance (::-webkit-scrollbar) for better user experience within main-item-block.
Usage:
Integrate the MainBlock component into your Vue.js application to provide a user-friendly interface for conducting searches and filtering results by categories. Customize styles and functionalities to meet specific project requirements and enhance user interaction.






