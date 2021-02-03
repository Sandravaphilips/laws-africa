<template>
    <article class="akoma-ntoso" id="bylaw">
      <div>
        <div class="coverpage">
          <div class="place-name">
            Cape Town<br />
            South Africa
          </div>
          <h1>Animal By-law, 2011</h1>
          <ul class="notice-list">
            <li class="publication-info">
              Published in
              <a
                href="https://edit.laws.africa/works/akn/za-cpt/act/by-law/2011/animal/media/publication/za-cpt-act-by-law-2011-animal-publication-document.pdf"
                >Province of Western Cape: Provincial Gazette no. 6896</a
              >
              on 5 August 2011
            </li>
            <li class="commencement-date">Commenced on 5 August 2011</li>
            <li class="as-at-date-notice">
              [Up to date as at 17 November 2020]
            </li>
          </ul>
        </div>
        <span class="akn-akomaNtoso">
          <article
            class="akn-act"
            data-contains="originalVersion"
            data-name="act"
          >
            <section class="akn-preamble" id="preamble">
              <h3>Preamble</h3>
              <span class="akn-p"
                >WHEREAS old municipalities within the area of jurisdiction of
                the City of Cape Town have been disestablished to form one
                municipality with legislative and executive powers over all
                areas of such old municipalities;</span
              >
              <span class="akn-p"
                >WHEREAS there is a need to develop one piece of legislation to
                govern the control of animals including dogs, cats and working
                equines uniformly throughout the City;</span
              >
              <span class="akn-p"
                >WHEREAS the City has competence in terms of the Constitution of
                the Republic of South Africa to make and administer by-laws for
                the effective administration of the matters which it has the
                right to administer;</span
              >
              <span class="akn-p"
                >WHEREAS the City has the competence in terms of Part B of
                Schedule 5 of the Constitution relating to control of public
                nuisances, pounds, facilities for the accommodation, care and
                burial of animals, licensing of dogs, municipal roads, traffic
                and parking and has the competence in terms of Part B of
                Schedule 4 of the Constitution relating to municipal health
                services;</span
              >
              <span class="akn-p"
                >AND NOW THEREFORE, be it enacted by the Council of the City of
                Cape Town, as follows:</span
              >
            </section>
            <span class="akn-body">
              <Chapter1 />
              <Chapter2 />
              <Chapter3 />
              <Chapter4 />
              <Chapter5 />
              <Chapter6 />
              <Chapter7 />
            </span>
          </article>
        </span>
      </div>
    </article>
</template>

<script>
import Chapter1 from "./chapters/Chapter1";
import Chapter2 from "./chapters/Chapter2";
import Chapter3 from "./chapters/Chapter3";
import Chapter4 from "./chapters/Chapter4";
import Chapter5 from "./chapters/Chapter5";
import Chapter6 from "./chapters/Chapter6";
import Chapter7 from "./chapters/Chapter7";

export default {
  name: "Contents",
  components: {
    Chapter1,
    Chapter2,
    Chapter3,
    Chapter4,
    Chapter5,
    Chapter6,
    Chapter7,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#bylaw {
  margin-left: 35%;
  padding: 20px 30px 20px 0;
  font-family: 'Lato', sans-serif;
  font-size: 18px;
  letter-spacing: -0.3px;
}

@media screen and (max-width: 800px) {
  #bylaw {
    margin: 30px;
    padding: 0;
  }
}
</style>
