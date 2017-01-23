# boilerpipe3
Python interface to Boilerpipe, Boilerplate Removal and Fulltext Extraction from HTML pages

Installation
============
    
    pip install JPype1 
    pip install charade
    python setup.py install

Configuration
=============

The boilerpipe jar files will get fetched and included automatically when building the package.

Usage
=====

Be sure to have set JAVA_HOME properly since jpype depends on this setting.

The constructor takes a keyword argment ``extractor``, being one of the available boilerpipe extractor types:

- DefaultExtractor
- ArticleExtractor
- ArticleSentencesExtractor
- KeepEverythingExtractor
- KeepEverythingWithMinKWordsExtractor
- LargestContentExtractor
- NumWordsRulesExtractor
- CanolaExtractor

If no extractor is passed the DefaultExtractor will be used by default. Additional keyword arguments are either ``html`` for HTML text or ``url``.

    from boilerpipe.extract import Extractor
    extractor = Extractor(extractor='ArticleExtractor', url=your_url)

Then, to extract relevant content:

    extracted_text = extractor.getText()
    extracted_html = extractor.getHTML()
