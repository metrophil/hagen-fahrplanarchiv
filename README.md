# Fahrplanarchiv für die Stadt Hagen
GTFS-based archive of bus and tram timetables in Hagen

The purpose of this repository is to create an interactive, GTFS-based archive of urban transport (bus and tram) timetables for the [city of Hagen, Germany](https://en.wikipedia.org/wiki/Hagen), mainly the services operated by *[Hagener Straßenbahn AG](https://www.hst-hagen.de/)*. Users will be able to research what the timetable of a route or a stop was in an individual year, search for connections in the past, compare timetables over time, and possibly find other metrics (e.g. how many km of tram or bus service were delivered each year, how many passengers were transported, etc.). If possible, the original scans or original PDF files may be available for download as well.

Other users without interest in Hagen may find interest in the tools created and/or used for comparisons of multiple GTFS files.

# Sources
Sources are mainly the timetable books published by Hagener Straßenbahn AG each year. The owner of the repository owns some older timetables. So far, others have been found available to be viewed and scanned at:
* [Municipal Archive of the City of Hagen](https://www.hagen.de/stadtarchiv)
* [archive and library of Deutsche Gesellschaft für Eisenbahngeschichte (DGEG)](https://dgeg.de/15-Archiv_und_Bibliothek) housed at [Technical University of Dortmund library](https://ub.tu-dortmund.de/)
* private timetable archive of Hagener Straßenbahn AG timetable department

More and contextualising information can be found in literature. The following books have been found to contain some information so far:
* Wolfgang Reimann, Rolf Löttgers: *Rund um Hagen.* Verlag Monika Reimann, Wuppertal 1989, ISBN 3-925298-06-1.
* Dirk Göbel, Jörg Rudat: *Bitte Einsteigen! – Mit der Straßenbahn durch Hagen.* ardenkuverlag, Hagen 2009, ISBN 978-3-932070-95-2.
* Dirk Göbel, Jörg Rudat: *Bitte Umsteigen! – Über Haspe und Voerde nach Breckerfeld – Mit der Linie 11 ins Grüne.* ardenkuverlag, Hagen 2012, ISBN 978-3-942184-08-3.
* Dirk Göbel, Jörg Rudat: *Bitte Zusteigen! – Von Hagen über Herdecke nach Wetter – Mit der Linie 4 von der Volme an die Ruhr.* ardenkuverlag, Hagen 2014, ISBN 978-3-942184-13-7.
* Dieter Höltge: *Straßen- und Stadtbahnen in Deutschland, Band 3 Westfalen.* EK-Verlag, Freiburg 1990, ISBN 3-88255-332-4.

Additionally, historic address books also sometimes contain information about public transport: *[Adressbücher der Stadt Hagen](https://wiki.genealogy.net/Kategorie:Adressbuch_f%C3%BCr_Hagen_(Westfalen))* on Verein für Computergenealogie's website.

# GTFS files
Each timetable period (usually about 6 or 12 months in length), for which a complete(*) timetable book (or scans/photos of it) are available, will need to be recreated as a static GTFS file. IDs will need to be created in a way, that a stop maybe identified over the course of many years, even when the name or even the location (slightly) changed.

The GTFS file should represent the standard timetable as depicted in the timetable book for the period for that it was valid. Changes due to e.g. construction should only be represented when specifically shown in the timetable book, even where e.g. for more recent years, information may be available what unplanned timetable changes occurred.

## Challenges with creating GTFS files
1. Most of the time, the actual timetable of route printed in a timetable book does not contain the departure times for all stops, some stops are omitted. This means that to create a complete GTFS file, the departure times for those omitted stops need to be interpolated. There should be a reasonably consistent approach in doing this.
2. The farther back in time the timetable is from, it has also already shown to be difficult to identify all the stops of a route. This is because in early timetables, there is usually no complete stop list for a route and no route map showing all stops. Stop locations and names will possibly need to be extrapolated using local knowledge of where stops were in later years or are today, or where a stop would have made sense at the time. It needs to be possible for users of the archive to identify where data is taken from an actual source, and where it has been basically "guessed".
3. Decisions also need to be made about the inclusion of railway services, and of routes of other operators. In early timetables, railway timetables are often just represented by listing all departures at Hagen Hauptbahnhof station. Only later, the actual railway routes are represented in the timetable. This could be remedied by researching railway timetables of the time, which would have more information about those services. For other operators' routes the challenge is mainly that in different timetable books, the scope of routes included varies.
4. The level of detail that is to be included in the exact GPS coordinates and in the route shapes also needs to be decided on. Over time, streets and their layout has changed, and also bigger stops (e.g. Hauptbahnhof and Stadtmitte) have had different configuration of platforms, bays and stands. While some of the knowledge can be taken from e.g. aerial imagery (using a [Hagen-based website](https://d3d9.xyz/projekte/geo/fsmap) collecting links to different historic aerial imagery services) or maps, it maybe difficult to reconstruct this for every timetable period with an appropriate level of validity.
5. There needs to be discussion in what way fare information should be included, if at all

# Todos
- [ ] Create concept of what the user interface should be able to do
- [ ] Create concept for software architecture
- [ ] Create 2-3 GTFS files to start experimenting
- [ ] Set up archive
- [ ] Find, scan or photograph more timetable books
- [ ] Continuously create more GTFS files to integrate into the archive
- [ ] Research copyright rules for uploading scans/photos of maps and timetable books

# Timetables to be included
The following timetable periods can immediately be recreated in GTFS, with scans, photos, or original timetable books already available to the creator of the repository:
* Winterfahrplan 1929/30
* Sommerfahrplan 1951
* Sommerfahrplan 1969
* 1975/76
* 1983/84
* 1989/90
* 2001/02
* from 7 January 2003
* from 10 March 2003
* from 2 June 2003
* from 3 August 2003
* all timetables since 2005
