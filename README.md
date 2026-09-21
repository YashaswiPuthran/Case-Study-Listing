**Case Studies Listing**

A filterable, sortable listing of Case Studies, built in Drupal. You can filter by Industry and Region, sort by newest/oldest/title, and everything updates in place with AJAX

**Getting it running**

You'll need Docker (or Colima/OrbStack) running, and DDEV installed.
git clone https://github.com/YashaswiPuthran/Case-Study-Listing.git
cd Case-Study-Listing
ddev start
ddev composer install

Then build the site straight from the committed config:
ddev drush site-install --existing-config -y
ddev drush uli

Once it's up, head to /case-studies. Add a few Case Study nodes with an Industry, a Region, and an image, and you'll see the filtering and sorting.

**Approach**

1. **Filtering and sorting** come from Views' own exposed filters and exposed sort criteria. I added Better Exposed Filters mainly for one thing core Views doesn't handle nicely on its own: getting "Newest / Oldest / Title A–Z" into a single dropdown instead of a "Sort by" field plus a separate Asc/Desc selector, which is what core gives you by default.
2. No full-page reload is just the view's built-in "Use AJAX" setting.
3. Industry and Region are taxonomy reference fields, so Views can filter and sort on them
4. Theme: a custom theme (case_studies_theme).
5. There's a case-study-card component for the actual card markup, plus two more components (filter, pager) that give the Views exposed form and pager some styling.


ETA:

Content type, fields, taxonomies - 15mins
View: filters, sort, AJAX, pager - 15mins
Theme + components + styling - 2h
Debugging - 30mins
Total - 3h

Screenshots:
Desktop:
<img width="1897" height="968" alt="image" src="https://github.com/user-attachments/assets/f7c32c7c-9366-4474-a6cb-0effc26bb084" />

Tab:
<img width="860" height="816" alt="image" src="https://github.com/user-attachments/assets/36095f56-a87e-4916-9032-391d5691be9b" />

Mobile:
<img width="1047" height="723" alt="image" src="https://github.com/user-attachments/assets/7b0fa648-dde6-47be-8bd6-f629e35d1d3c" />


Filter:
<img width="1432" height="602" alt="image" src="https://github.com/user-attachments/assets/ef54d925-447b-4721-ab96-f6a7f35f9771" />

Pager:
<img width="1372" height="633" alt="image" src="https://github.com/user-attachments/assets/d28530f3-9041-4350-bf40-1003842e1a3c" />




