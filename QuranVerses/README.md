# QuranVerses
#Quran Verses .NET Assembly

#This assembly contains all Quran verses hardcoded in Bosnian, English and German language.

Quran class properties:

    // Returns all 6236 verses in Bosnian
    public List<string> AllVersesBosnian   
    
    // Returns all 6236 verses in English
    public List<string> AllVersesEnglish 
    
    // Returns all 6236 verses in German
    public List<string> AllVersesGerman 
    
    // Returns all Surahs verses in all 3 languages as "Surah" objects
    public List<Surah> AllSurahBihEngDe 
    
    
    
#Quran class public methods:

// Returns all verses of specified Surah by number and specified language
public List<string> GetVerses(int surahNumberParam, string languageParam)

#Method Parameters:
int surahNumberParam - 1-114
string languageParam - "bih", "en", "de" or Constants.LanguageBosnian,Constants.LanguageEnglish and Constants.LanguageGerman



#Surah class:
public class Surah
{
    public string Name { get; set; }

    public int Number { get; set; }

    public List<Verse> VerseList { get; set; }
}

#Verse class:
public class Verse
{
    public int Number { get; set; }
    public string TextBosnian { get; set; }
    public string TextEnglish { get; set; }
    public string TextGerman { get; set; }
}

#Examples:
// include namespace
using QuranVerses;

// instantiate Quran class
Quran quran = new Quran();

 // Populate listbox with verses from surah nr 1 in bosnian
 listBox1.DataSource = quran.GetVerses(1,Constants.LanguageBosnian);

 // Populate listbox with verses from surah nr 1 in english
 listBox1.DataSource = quran.GetVerses(1,Constants.LanguageEnglish);

 // Populate listbox with verses from surah nr 1 in german
 listBox1.DataSource = quran.GetVerses(1,Constants.LanguageGerman);


 // Populate listbox with all 6236 verses from Quran in bosnian
 listBox1.DataSource = quran.AllVersesBosnian;


 // Populate listbox with all 6236 verses from Quran in english
 listBox1.DataSource = quran.AllVersesEnglish;

            
 // Populate listbox with all 6236 verses from Quran in german
 listBox1.DataSource = quran.AllVersesGerman;
            
 // All 114 Surahs as objects with all verses
 List<Surah> allSurahs = quran.AllSurahBihEngDe;
 
 // Example: Surah 47 Verse 1 in Bosnian
 textBoxBih.Text = allSurahs[47].VerseList[1].TextBosnian;

