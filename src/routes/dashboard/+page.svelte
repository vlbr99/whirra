<script>
  import "../dashboard/dashboard.scss";
  import JwtGenerator from "../components/jwt_generator/Jwt_generator.svelte";
  import Regex from "../components/regex/Regex.svelte";
  import Icons from "../components/icons/Icons.svelte";
  import Badge from "../components/Badge/Badge.svelte";
  import Fonts from "../components/Fonts/Fonts.svelte";
  import UserModel from "../components/user_model/User_model.svelte";
  import ReportModel from "../components/report_model/Report_model.svelte";
  import ContactModel from "../components/contact_model/Contact_model.svelte";
  import PlaceholderImages from "../components/placeholder_images/Placeholder_images.svelte";
  import BoxShadows from "../components/Box_shadows/Box_shadows.svelte";
  import Link from "../components/Link/Link.svelte";
  import Preheader from "../components/Preheader/Preheader.svelte";
  import Button from "../components/Button/Button.svelte";
  import PostFooter from "../components/post_footer/Post_footer.svelte";
  import MicroCard from "../components/micro_card/Micro_card.svelte";
  import MiniCard from "../components/mini_card/Mini_card.svelte";
  import Input from "../components/Input/Input.svelte";
  import Textarea from "../components/textarea/Textarea.svelte";
  import Cb from "../components/Checkbox/Cb.svelte";
  import Rg from "../components/Rg/Rg.svelte";
  import Switch from "../components/Switch/Switch.svelte";
  import Select from "../components/Select/Select.svelte";
  import About from "../components/About/About.svelte";
  import Menu from "lucide-svelte/icons/menu";
  import Install from "../components/Install/Install.svelte";
  import Carousel from "../components/Carousel/Carousel.svelte";
  import AccordionTest from "../components/Accordion/Accordion_test.svelte";
  import Tabs from "../components/tabs/Tabs.svelte";
  import TabsTest from "../components/tabs/Tabs_test.svelte";
  import CardTest from "../components/Card/Card_test.svelte";
  import Footer from "../components/Footer/Footer.svelte";
  import Header from "../components/Header/Header.svelte";
  import Toast from "../components/toast/Toast.svelte";
  import ToastTest from "../components/toast/Toast_test.svelte";
  import AlertTest from "../components/alert/Alert_test.svelte";
  import Forum from "../components/Forum_schema/Forum.svelte";
  const components = {
    jwt: JwtGenerator,
    regex: Regex,
    icons: Icons,
    badge: Badge,
    fonts: Fonts,
    userModel: UserModel,
    reportModel: ReportModel,
    contactModel: ContactModel,
    placeholderImages: PlaceholderImages,
    bs: BoxShadows,
    link: Link,
    ph: Preheader,
    btn: Button,
    pf: PostFooter,
    mc: MicroCard,
    mini: MiniCard,
    input: Input,
    tarea: Textarea,
    install: Install,
    cb: Cb,
    forum: Forum,
    rg: Rg,
    switch: Switch,
    select: Select,
    ab: About,
    c: Carousel,
    acc: AccordionTest,
    tabs: TabsTest,
    card: CardTest,
    footer: Footer,
    header: Header,
    toast: ToastTest,
    alert: AlertTest,
  };

  let currentComponent = Install;

  function selectComponent(key) {
    currentComponent = components[key];
  }
</script>

<div class="dashboard_wrapper">
  <button class="menu_toggle">
    <Menu />
  </button>
  <aside>
    <p>About Whirra</p>
    <ul>
      <li>
        <button
          onclick={() => {
            selectComponent("ab");
          }}>What is Whirra</button
        >
      </li>
    </ul>
    <p>Get started*</p>
    <ul>
      <li>
        <button
          onclick={() => {
            selectComponent("install");
          }}>Installation</button
        >
      </li>
    </ul>
    <p>Frontend*</p>
    <ul>
      <li>
        <button
          onclick={() => {
            selectComponent("bs");
          }}>Box Shadows</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("fonts");
          }}
        >
          Fonts <span>new</span>
        </button>
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("icons");
          }}
        >
          Icons <span>new</span>
        </button>
      </li>
    </ul>
    <i>UI components</i>
    <ul>
      <li>
        <button
          onclick={() => {
            selectComponent("acc");
          }}>Accordion</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("alert");
          }}>Alert dialog</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("badge");
          }}
        >
          Badge <span>new</span>
        </button>
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("btn");
          }}>Button</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("card");
          }}>Card</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("c");
          }}>Carousel</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("cb");
          }}
        >
          Checkbox
        </button>
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("footer");
          }}>Footer</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("header");
          }}>Header</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("input");
          }}>Input</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("link");
          }}
        >
          Link
        </button>
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("mc");
          }}>Micro card</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("mini");
          }}>Mini card</button
        >
      </li>
      <li>Popover <span class="soon_2">soon</span></li>
      <li>
        <button
          onclick={() => {
            selectComponent("pf");
          }}>Postfooter</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("ph");
          }}
        >
          Preheader
        </button>
      </li>
      <li>Progress <span class="soon_2">soon</span></li>
      <li>
        <button
          onclick={() => {
            selectComponent("rg");
          }}>Radio group</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("select");
          }}>Select</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("switch");
          }}>Switch</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("tabs");
          }}>Tabs</button
        >
      </li>
      <li>Testimonial <span class="soon_2">soon</span></li>
      <li>
        <button
          onclick={() => {
            selectComponent("tarea");
          }}
        >
          Textarea
        </button>
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("toast");
          }}>Toast</button
        >
      </li>
      <li>Tooltip <span class="soon_2">soon</span></li>
    </ul>
    <p>Backend*</p>
    <ul>
      <li>
        <button
          onclick={() => {
            selectComponent("jwt");
          }}>JWT secret generator</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("regex");
          }}
        >
          Regex snippets
        </button>
      </li>
    </ul>
    <p>Database*</p>
    <ul>
      <li>
        <button
          onclick={() => {
            selectComponent("contactModel");
          }}
        >
          Mongoose contact schema
        </button>
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("forum");
          }}>Mongoose forum schema</button
        >
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("reportModel");
          }}
        >
          Mongoose report schema
        </button>
      </li>
      <li>
        <button
          onclick={() => {
            selectComponent("userModel");
          }}
        >
          Mongoose user schema
        </button>
      </li>
    </ul>
  </aside>

  <main>
    {#if currentComponent}
      <svelte:component this={currentComponent} />
    {/if}
  </main>
</div>
<div class="resp">
  <p>/dashboard is not available on mobile devices</p>
</div>
