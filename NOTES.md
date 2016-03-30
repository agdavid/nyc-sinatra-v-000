Models:

1) class Landmark
      belongs_to :figure

2) class Title
      has_many :figure_titles
      has_many :figures, through: :figure_titles

3) class Figure
      has_many :landmarks
      has_many :figure_titles
      has_many :titles, through :figure_titles

4) class FigureTitles
      belongs_to :figure
      belongs_to :title

Controllers:

1) class LandmarksController
    index page => index.erb of all landmarks
    new page => new.erb to create a landmark
    edit page => edit.erb to edit a landmark
    show page => show.erb to show a created or edited landmark

2) class FiguresController
    figure page => index.erb of all figures
    new page => new.erb to create a figure
        AND
            select or create new landmark
            select or create new title

3) NO TitlesController

Migrations:

1) figures: name (string)
2) landmarks: name (string), 
    figure_id (integer), 
    year_completed (integer)
3) titles: name(string)
4) figure_titles: title_id (integer), figure_id (integer)

