---
license: apache-2.0
---



# MMDocIR Evaluation Set



## Dataset Overview

**MMDocIR** evaluation set includes 313 long documents averaging 65.1 pages, categorized into ten main domains: research reports, administration&industry, tutorials&workshops, academic papers, brochures, financial reports, guidebooks, government documents, laws, and news articles. 
Different domains feature distinct distributions of multi-modal information. Overall, the modality distribution is: Text (60.4%), Image (18.8%), Table (16.7%), and other modalities (4.1%).

**MMDocIR** evluation set encompasses 1,658 questions, 2,107 page labels, and 2,638 layout labels. The modalities required to answer these questions distribute across four categories: Text (44.7%), Image (21.7%), Table (37.4%), and Layout/Meta (11.5%). The ``Layout/Meta'' category encompasses questions related to layout information and meta-data statistics. 
Notably, the dataset poses several challenges: 254 questions necessitate cross-modal understanding, 313 questions demand evidence across multiple pages, and 637 questions require reasoning based on multiple layouts. These complexities highlight the need for advanced multi-modal reasoning and contextual understanding.



## Important Notice

**MMDocIR** will be used as evaluation set for Multi-modal Information Retrieval Challenge ([MIRC](https://erel-mir.github.io/challenge/)) in Web Conference 2025. Thus, the annotation will be temporarily held out for challenge evaluation. It will be released publicly after the challenge submission deadline.



## Dataset Structure

1. `MMDocIR_questions.jsonl` contains all questions and its relevant information.

   ```
   features:
     - name: doc_name
       dtype: string
     - name: domain
       dtype: string
     - name: num_of_pages
       dtype: integer
     - name: num_of_layouts
       dtype: integer
     - name: questions
       dtype: list[string]
   ```

2. `page_images.rar` contains 20,395 document page screenshots from 313 documents.

3. `layout_images.rar` contains 14,826 images cropped from 313 documents. Each image is can be a chart, figure, table, etc.

4. `page_content` contains 313 json-line files, each containing all relevant page information within the one document.

   ```
   features:
     - name: page
       dtype: integer
     - name: image_path
       dtype: string
     - name: ocr_text
       dtype: string
     - name: vlm_text
       dtype: string
   ```

5. `layout_content` contains 313 json-line files, each containing all relevant layout information within the one document.

   ```
   features:
     - name: layout
       dtype: integer
     - name: type
       dtype: string
     - name: page_idx
       dtype: integer
     - name: bbox
       dtype: list[integer]
     - name: page_size
       dtype: list[integer]
     - name: layout
       dtype: integer
       
   Optional features:
     - name: img_path
       dtype: string
     - name: img_caption
       dtype: string
     - name: ocr_text
       dtype: string
     - name: vlm_text
       dtype: string
   ```



## Citation Information

If you use this dataset in your research, please cite the original dataset as follows:

```
@misc{dong2025mmdocirbenchmarkingmultimodalretrieval,
      title={MMDocIR: Benchmarking Multi-Modal Retrieval for Long Documents}, 
      author={Kuicai Dong and Yujing Chang and Xin Deik Goh and Dexun Li and Ruiming Tang and Yong Liu},
      year={2025},
      eprint={2501.08828},
      archivePrefix={arXiv},
      primaryClass={cs.IR},
      url={https://arxiv.org/abs/2501.08828}, 
}
```



