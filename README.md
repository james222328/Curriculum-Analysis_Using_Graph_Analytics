# Course Graph Analysis and Community Detection

This project leverages Python and graph theory to analyze MSc course data extracted from PDFs. It builds and visualizes relationships between courses based on their textual descriptions using cosine similarity and network graph representations. Additionally, it supports community detection to identify closely related groups of courses.

---

## Features

### 1. **PDF Text Extraction**
- Extracts text content from PDFs using `PyMuPDF`.
- Handles multiple PDFs containing course details.

### 2. **Course Data Parsing**
- Identifies and extracts course codes, titles, and descriptions using regular expressions.
- Structures the extracted data into a dictionary format for analysis.

### 3. **Cosine Similarity Analysis**
- Computes TF-IDF vectors for course descriptions.
- Calculates cosine similarity between courses to determine relationships.

### 4. **Graph Construction and Visualization**
- Constructs graphs where nodes represent courses and edges represent similarity relationships.
- Supports:
  - Full graph visualization with high-similarity edges.
  - Sub-graph visualization for a specific course and its neighbors.

### 5. **Combined Graph Analysis**
- Combines multiple graphs representing different datasets.
- Visualizes the combined relationships and identifies overlapping courses.

### 6. **Community Detection**
- Uses the Louvain method for community detection.
- Highlights communities in the graph visualization.

---

## Installation

### Prerequisites
- Python 3.8 or higher
- Install required libraries:
  ```bash
  pip install PyMuPDF scikit-learn matplotlib networkx python-louvain
  ```

---

## Usage

### 1. Extract and Analyze a Single PDF
1. Place the PDF in your working directory.
2. Update the `pdf_path` variable with the file path:
   ```python
   pdf_path = '/path/to/your/pdf/file.pdf'
   ```
3. Run the following to extract data and generate a graph:
   ```python
   courses, subjects, course_titles, edges = nngd(pdf_path)
   G = pmg(course_titles, edges)
   ```

### 2. Visualize Specific Course Relationships
To visualize a sub-graph for a specific course:
```python
specific_title = 'COURSE TITLE'
psp(G, specific_title)
```

### 3. Combine Multiple Graphs
To analyze and visualize combined graphs:
```python
combined_graph = create_combined_graph([G1, G2, G3])
plot_combined_graph(combined_graph, title="Combined Graph")
```

### 4. Perform Community Detection
To detect and visualize communities in the graph:
```python
detect_and_plot_communities(combined_graph, title="Community Detection")
```

---

## Workflow

### Step 1: Extract Course Data
- Extracts and parses text content from PDFs to identify course details.

### Step 2: Compute Similarity
- TF-IDF vectorization and cosine similarity computation for course descriptions.

### Step 3: Generate Graphs
- Builds a graph where nodes are course titles and edges represent similarity.

### Step 4: Visualize Relationships
- Visualizes full and sub-graphs of courses.

### Step 5: Combine Graphs
- Merges multiple graphs for comprehensive analysis.

### Step 6: Detect Communities
- Uses the Louvain algorithm to identify clusters of closely related courses.

---

## Example Outputs

1. **Graph Visualization**
   - Displays nodes (courses) and edges (relationships) with high similarity.
   - Highlights important nodes based on centrality.

2. **Community Detection**
   - Identifies and colors clusters of closely related courses.

---

## Dependencies

- `PyMuPDF` - PDF text extraction
- `scikit-learn` - TF-IDF vectorization and cosine similarity
- `networkx` - Graph construction and analysis
- `matplotlib` - Visualization
- `python-louvain` - Community detection

---

## Contributions

Contributions are welcome! Feel free to fork the repository, make improvements, and submit a pull request.

---

## License

This project is licensed under the MIT License.

---

